# Q1)What does List component does ?
## Ans:- 
### List is a component of react which is taking an array of items which contains unordered list of item and rendering each element of the items array i.e. each item present by sending each to a component SingleListItem .

### The SingleListItem takes onClickHandler function, index, isSelected, text as props. 

### The onClickHandler functions sets the index of current item in selectedIndex , index props is to keep the index of current element, isSelected to check wether the index selected is current item index or not, text contains the content of the item.

### The WrappedSingleListItem is a higher-order component that wraps the SingleListItem component using React.memo. This optimizes performance by re-rendering the component only when its props changes.

### The WrappedListComponent is also a higher-order component that wraps the List component using React.memo due to optimization.

### The List component uses hooks like useState and useEffect. Whenever items props will change then useEffect hook will make the selectedIndex state to null. The useState hook is used to manage the selected index of the list item.

# Q2) What problems/errors are there in the code?
## Ans:-
### 1.	In the List component, the selectedIndex state variable isn’t initialized with a default value which isn’t recommended as it can create issues during mounting of the component.

### 2.	Secondly, while passing the isSelected props we should pass it as a Boolean value, comparing wether the selectedIndex value matches with the index of current item or not.

### 3.	Third, in the WrapListComponent, the PropTypes declaration for the items prop isn’t correct. The array prop type should be defined as “PropTypes.arrayOf” instead of “PropTypes.array”. 
###      Also the “PropTypes.shapeOf” should be “PropTypes.shape”.

 ### 4.	The WrappedListComponent should be memorized using React.memo instead of memo.
 
 ### 5.	In the SingleListItem component the “onClick” prop is not set correctly. The onClick prop should be set to a function that calls the ‘onClickHandler’ function with index of item as argument.

### 6. Each item should have a unique key in the mapping of items array because it helps react to keep track of all the items uniquely.

