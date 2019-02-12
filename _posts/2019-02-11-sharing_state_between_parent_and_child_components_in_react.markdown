---
layout: post
title:      "Sharing State Between Parent and Child Components in React"
date:       2019-02-12 02:15:01 +0000
permalink:  sharing_state_between_parent_and_child_components_in_react
---


Managing application and component state is the name of the game if we are talking React.

In a typical React app or app with large React portions you probably also have nesting of components.  Naturally at some point you are going to need to share State from Child to Parent and Parent to child.

Working on my increasingly consuming Non-Flatiron project [your-timelogs](https://your-timelog.herokuapp.com/) today I came across a problem that made for a good example to explain how state is shared in React.

One of the routes in this app is for a reports page, the reports page is intended to help the user visualize how they have spent their logged time over the past week or month.

Each default time period has a pair of graphs and legend that look like this:

![](https://i.imgur.com/ian7Alf.gif)

To start the day off I only had the top Pie chart and the legend.  The Pie Chart was in its own component and the legend is a functional component residing in a method of the time-pie class.
```
<Timepie beg={this.today} lookback={7}  />
```
```
ChartLegend = (data)=>{
    return (
        <table>
        <tbody>
            {
                data.map((x,i)=>{
                    return (
                    <tr key={i} onClick={()=>{this.props.ChangeSelectEvent(x)}}>
                        <td> <div className="legendSquare" ></div> </td>
                        <td>{x.label}</td>
                        <td>{x.value}</td>
                        <td>hours</td>
                    </tr>)
                    }
                )
            }
        </tbody>
        </table>
    )
}
```

A common method for chaning the state of a parent from an event inside a child is to pass a function defined on the parent as a prop to the child then tie that prop to an event on an element on the child that is done like so:
```
export default class reports extends React.Component{
...
    ChangeSelectEventWeekly = (sel)=>{
        this.setState({SelectedWeekly:sel})
    }

    render {
        return(
            <Timepie ...ChangeSelectEvent={this.ChangeSelectEventWeekly} />
            )
    }
}
```

see how ChangeSelectEventWeekly changes the state of reports, but is sent to Timepie as a prop, then inside of the legend we attach to eachr of the tr elements

```
 onClick={()=>{this.props.ChangeSelectEvent(x)}}

```
x in this instance is a object containing information about the item on the legend.





