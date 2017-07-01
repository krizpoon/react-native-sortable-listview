# react-native-sortable-listview
Drag drop capable wrapper of ListView for React Native. Allows for dragging and dropping of rows with automatic scrolling while dragging.

## Add it to your project

1. Run `npm install react-native-sortable-listview --save`
2. `import SortableListView from 'react-native-sortable-listview'`

## Demo

<a href="https://raw.githubusercontent.com/deanmcpherson/react-native-sortable-listview/master/demo.gif"><img src="https://raw.githubusercontent.com/deanmcpherson/react-native-sortable-listview/master/demo.gif" width="350"></a>

## Basic usage

See [example](example.js).

## Example

See [Sortable](Sortable).


## Props

SortableListView passes through all the standard ListView properties to ListView, except for dataSource. The renderRow method must render a component that forwards onLongPress and onPressOut methods to a Touchable* child component.  Calling the onLongPress method will enable the drag and drop on the row and onPressOut will cancel it. You can also apply the default behaviour by spreading the sortHandlers prop (e.g. `<TouchableHightlight {...this.props.sortHandlers} >..`)

 - **`onRowMoved`** _(Function)_ - should return a function that is passed a single object when a row is dropped. The object contains three properties `from`, `to`, and `row`. `from` and `to` are the order indexes being requested to move. `row` is all the info available about the row being dropped.
 - **`data`** _(Object)_ - Takes an object.
 - **`rowHasChanged`** _(Function)_ - Takes an function that is called to compare row data. It is passed the new row data and a shallow copy of the previous row data. **This is necessary to define if row data is not immutible for row changes to correctly propagate, if your row data is immutable DO NOT DEFINE, see #28 for reasons why**.
 - **`order`** _(Array)_  (optional) - Expects an array of keys to determine the current order of rows.
 - **`sortRowStyle`** _(Object)_ (optional) - Expects a `style` object, which is to be applied on the rows when they're being dragged.
 - **`disableSorting`** _(boolean) (optional) - When set to true, all sorting will be disabled, which will effectively make the SortableListView act like a normal ListView.
 - **`onMoveStart`** _(Function)_ (Optional) - Register a handler to be called when drag start.
 - **`onMoveEnd`** _(Function)_ (Optional) - Register a handler to be called when move is completed.

## methods

- **`scrollTo(...args)`** - Scrolls to a given x, y offset, either immediately or with a smooth animation. See ScrollView's scrollTo method.

---

### Contributions welcome!

---

**MIT Licensed**
