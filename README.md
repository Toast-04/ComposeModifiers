# Compose Modifiers Reference

## Actions

### anchoredDraggable
**Scope:** Any

```kotlin
<T : Any?> Modifier.anchoredDraggable(
state: AnchoredDraggableState<T>,
orientation: Orientation,
enabled: Boolean,
interactionSource: MutableInteractionSource?,
overscrollEffect: OverscrollEffect?,
flingBehavior: FlingBehavior?
)
```
Enable drag gestures between a set of predefined values.

---

### clickable
**Scope:** Any

```kotlin
Modifier.clickable(
    enabled: Boolean,
    onClickLabel: String?,
role: Role?,
interactionSource: MutableInteractionSource?,
onClick: () -> Unit
)
```
Configure component to receive clicks via input or accessibility "click" event.

---

### clickable (with indication)
**Scope:** Any

```kotlin
Modifier.clickable(
    interactionSource: MutableInteractionSource?,
indication: Indication?,
enabled: Boolean,
onClickLabel: String?,
role: Role?,
onClick: () -> Unit
)
```
Configure component to receive clicks via input or accessibility "click" event.

---

### combinedClickable
**Scope:** Any

```kotlin
Modifier.combinedClickable(
    enabled: Boolean,
    onClickLabel: String?,
role: Role?,
onLongClickLabel: String?,
onLongClick: (() -> Unit)?,
onDoubleClick: (() -> Unit)?,
hapticFeedbackEnabled: Boolean,
interactionSource: MutableInteractionSource?,
onClick: () -> Unit
)
```
Configure component to receive clicks, double clicks and long clicks via input or accessibility "click" event.

---

### draggable
**Scope:** Any

```kotlin
Modifier.draggable(
    state: DraggableState,
    orientation: Orientation,
    enabled: Boolean,
    interactionSource: MutableInteractionSource?,
startDragImmediately: Boolean,
onDragStarted: suspend CoroutineScope.(startedPosition: Offset) -> Unit,
onDragStopped: suspend CoroutineScope.(velocity: Float) -> Unit,
reverseDirection: Boolean
)
```
Configure touch dragging for the UI element in a single Orientation.

---

### draggable2D
**Scope:** Any

```kotlin
Modifier.draggable2D(
    state: Draggable2DState,
    enabled: Boolean,
    interactionSource: MutableInteractionSource?,
startDragImmediately: Boolean,
onDragStarted: (startedPosition: Offset) -> Unit,
onDragStopped: (velocity: Velocity) -> Unit,
reverseDirection: Boolean
)
```
Configure touch dragging for the UI element in both orientations.

---

### selectable
**Scope:** Any

```kotlin
Modifier.selectable(
    selected: Boolean,
    enabled: Boolean,
    role: Role?,
interactionSource: MutableInteractionSource?,
onClick: () -> Unit
)
```
Configure component to be selectable, usually as a part of a mutually exclusive group, where only one item can be selected at any point in time.

---

### selectableGroup
**Scope:** Any

```kotlin
Modifier.selectableGroup()
```
Use this modifier to group a list of selectable items like Tabs or RadioButtons together for accessibility purpose.

---

### toggleable
**Scope:** Any

```kotlin
Modifier.toggleable(
    value: Boolean,
    enabled: Boolean,
    role: Role?,
interactionSource: MutableInteractionSource?,
onValueChange: (Boolean) -> Unit
)
```
Configure component to make it toggleable via input and accessibility events.

---

### triStateToggleable
**Scope:** Any

```kotlin
Modifier.triStateToggleable(
    state: ToggleableState,
    enabled: Boolean,
    role: Role?,
interactionSource: MutableInteractionSource?,
onClick: () -> Unit
)
```
Configure component to make it toggleable via input and accessibility events with three states: On, Off and Indeterminate.

---

## Alignment

### align (Row)
**Scope:** RowScope

```kotlin
Modifier.align(alignment: Alignment.Vertical)
```
Align the element vertically within the Row.

---

### align (Column)
**Scope:** ColumnScope

```kotlin
Modifier.align(alignment: Alignment.Horizontal)
```
Align the element horizontally within the Column.

---

### align (Box)
**Scope:** BoxScope

```kotlin
Modifier.align(alignment: Alignment)
```
Pull the content element to a specific Alignment within the Box.

---

### alignBy (Row)
**Scope:** RowScope

```kotlin
Modifier.alignBy(alignmentLineBlock: (Measured) -> Int)
```
Position the element vertically such that the alignment line for the content as determined by alignmentLineBlock aligns with sibling elements also configured to alignBy.

---

### alignByBaseline
**Scope:** RowScope

```kotlin
Modifier.alignByBaseline()
```
Position the element vertically such that its first baseline aligns with sibling elements also configured to alignByBaseline or alignBy.

---

## Animation

### animateBounds
**Scope:** Any

```kotlin
Modifier.animateBounds(
    lookaheadScope: LookaheadScope,
    modifier: Modifier,
    boundsTransform: BoundsTransform,
    animateMotionFrameOfReference: Boolean
)
```
Modifier to animate layout changes (position and/or size) that occur within a LookaheadScope.

---

### animateEnterExit
**Scope:** AnimatedVisibilityScope

```kotlin
Modifier.animateEnterExit(
    enter: EnterTransition,
    exit: ExitTransition,
    label: String
)
```
animateEnterExit modifier can be used for any direct or indirect children of AnimatedVisibility to create a different enter/exit animation than what's specified in AnimatedVisibility.

---

### animateItem (LazyList)
**Scope:** LazyItemScope

```kotlin
Modifier.animateItem(
    fadeInSpec: FiniteAnimationSpec<Float>?,
placementSpec: FiniteAnimationSpec<IntOffset>?,
fadeOutSpec: FiniteAnimationSpec<Float>?
)
```
This modifier animates the item appearance (fade in), disappearance (fade out) and placement changes (such as an item reordering).

---

### animateContentSize
**Scope:** Any

```kotlin
Modifier.animateContentSize(
    animationSpec: FiniteAnimationSpec<IntSize>,
finishedListener: ((initialValue: IntSize, targetValue: IntSize) -> Unit)?
)
```
This modifier animates its own size when its child modifier (or the child composable if it is already at the tail of the chain) changes size.

---

## Border

### border
**Scope:** Any

```kotlin
Modifier.border(border: BorderStroke, shape: Shape)
```
Modify element to add border with appearance specified with a border and a shape and clip it.

```kotlin
Modifier.border(width: Dp, color: Color, shape: Shape)
```
Modify element to add border with appearance specified with a width, a color and a shape and clip it.

```kotlin
Modifier.border(width: Dp, brush: Brush, shape: Shape)
```
Modify element to add border with appearance specified with a width, a brush and a shape and clip it.

---

## Drawing

### alpha
**Scope:** Any

```kotlin
Modifier.alpha(alpha: Float)
```
Draw content with modified alpha that may be less than 1.

---

### background
**Scope:** Any

```kotlin
Modifier.background(color: Color, shape: Shape)
```
Draws shape with a solid color behind the content.

```kotlin
Modifier.background(brush: Brush, shape: Shape, alpha: Float)
```
Draws shape with brush behind the content.

---

### clip
**Scope:** Any

```kotlin
Modifier.clip(shape: Shape)
```
Clip the content to shape.

---

### drawBehind
**Scope:** Any

```kotlin
Modifier.drawBehind(onDraw: DrawScope.() -> Unit)
```
Draw into a Canvas behind the modified content.

---

### drawWithContent
**Scope:** Any

```kotlin
Modifier.drawWithContent(onDraw: ContentDrawScope.() -> Unit)
```
Creates a DrawModifier that allows the developer to draw before or after the layout's contents.

---

### shadow
**Scope:** Any

```kotlin
Modifier.shadow(
    elevation: Dp,
    shape: Shape,
    clip: Boolean,
    ambientColor: Color,
    spotColor: Color
)
```
Creates a graphicsLayer that draws a shadow.

---

### dropShadow
**Scope:** Any

```kotlin
Modifier.dropShadow(shape: Shape, shadow: Shadow)
```
Draws a drop shadow behind the rest of the content with the geometry specified by the given shape and the shadow properties defined by the Shadow.

---

### innerShadow
**Scope:** Any

```kotlin
Modifier.innerShadow(shape: Shape, shadow: Shadow)
```
Draws an inner shadow on top of the rest of the content with the geometry specified by the given shape and the shadow properties defined by the Shadow.

---

## Focus

### focusable
**Scope:** Any

```kotlin
Modifier.focusable(
    enabled: Boolean,
    interactionSource: MutableInteractionSource?
)
```
Configure component to be focusable via focus system or accessibility "focus" event.

---

### focusTarget
**Scope:** Any

```kotlin
Modifier.focusTarget()
```
Add this modifier to a component to make it focusable.

---

### focusRequester
**Scope:** Any

```kotlin
Modifier.focusRequester(focusRequester: FocusRequester)
```
Add this modifier to a component to request changes to focus.

---

### onFocusChanged
**Scope:** Any

```kotlin
Modifier.onFocusChanged(onFocusChanged: (FocusState) -> Unit)
```
Add this modifier to a component to observe focus state events.

---

## Size

### size
**Scope:** Any

```kotlin
Modifier.size(size: Dp)
```
Declare the preferred size of the content to be exactly size dp square.

```kotlin
Modifier.size(width: Dp, height: Dp)
```
Declare the preferred size of the content to be exactly width dp by height dp.

---

### width / height
**Scope:** Any

```kotlin
Modifier.width(width: Dp)
Modifier.height(height: Dp)
```
Declare the preferred width/height of the content to be exactly the specified dp.

---

### fillMaxWidth / fillMaxHeight / fillMaxSize
**Scope:** Any

```kotlin
Modifier.fillMaxWidth(fraction: Float = 1.0f)
Modifier.fillMaxHeight(fraction: Float = 1.0f)
Modifier.fillMaxSize(fraction: Float = 1.0f)
```
Have the content fill (possibly only partially) the max constraints.

---

### wrapContentWidth / wrapContentHeight / wrapContentSize
**Scope:** Any

```kotlin
Modifier.wrapContentWidth(align: Alignment.Horizontal, unbounded: Boolean)
Modifier.wrapContentHeight(align: Alignment.Vertical, unbounded: Boolean)
Modifier.wrapContentSize(align: Alignment, unbounded: Boolean)
```
Allow the content to measure at its desired size without regard for the incoming minimum constraints.

---

### aspectRatio
**Scope:** Any

```kotlin
Modifier.aspectRatio(
    ratio: Float,
    matchHeightConstraintsFirst: Boolean
)
```
Attempts to size the content to match a specified aspect ratio.

---

### defaultMinSize
**Scope:** Any

```kotlin
Modifier.defaultMinSize(minWidth: Dp, minHeight: Dp)
```
Constrain the size of the wrapped layout only when it would be otherwise unconstrained.

---

### weight (Row/Column)
**Scope:** RowScope / ColumnScope

```kotlin
Modifier.weight(weight: Float, fill: Boolean)
```
Size the element's width/height proportional to its weight relative to other weighted sibling elements.

---

## Padding

### padding
**Scope:** Any

```kotlin
Modifier.padding(all: Dp)
Modifier.padding(horizontal: Dp, vertical: Dp)
Modifier.padding(start: Dp, top: Dp, end: Dp, bottom: Dp)
Modifier.padding(paddingValues: PaddingValues)
```
Apply additional space along each edge of the content.

---

### absolutePadding
**Scope:** Any

```kotlin
Modifier.absolutePadding(left: Dp, top: Dp, right: Dp, bottom: Dp)
```
Apply additional space along each edge of the content in Dp (does not consider layout direction).

---

### System Insets Padding

```kotlin
Modifier.statusBarsPadding()
Modifier.navigationBarsPadding()
Modifier.systemBarsPadding()
Modifier.imePadding()
Modifier.safeDrawingPadding()
Modifier.captionBarPadding()
```
Adds padding to accommodate various system insets.

---

## Scroll

### scrollable
**Scope:** Any

```kotlin
Modifier.scrollable(
    state: ScrollableState,
    orientation: Orientation,
    enabled: Boolean,
    reverseDirection: Boolean,
    flingBehavior: FlingBehavior?,
interactionSource: MutableInteractionSource?
)
```
Configure touch scrolling and flinging for the UI element in a single Orientation.

---

### verticalScroll / horizontalScroll
**Scope:** Any

```kotlin
Modifier.verticalScroll(
    state: ScrollState,
    enabled: Boolean,
    flingBehavior: FlingBehavior?,
reverseScrolling: Boolean
)
```
Modify element to allow vertical/horizontal scrolling when height/width of the content is bigger than max constraints allow.

---

### nestedScroll
**Scope:** Any

```kotlin
Modifier.nestedScroll(
    connection: NestedScrollConnection,
    dispatcher: NestedScrollDispatcher?
)
```
Modify element to make it participate in the nested scrolling hierarchy.

---

## Pointer Input

### pointerInput
**Scope:** Any

```kotlin
Modifier.pointerInput(key1: Any?, block: PointerInputEventHandler)
Modifier.pointerInput(vararg keys: Any?, block: PointerInputEventHandler)
```
Create a modifier for processing pointer input within the region of the modified element.

---

### pointerHoverIcon
**Scope:** Any

```kotlin
Modifier.pointerHoverIcon(
    icon: PointerIcon,
    overrideDescendants: Boolean
)
```
Modifier that lets a developer define a pointer icon to display when the cursor is hovered over the element.

---

## Semantics

### semantics
**Scope:** Any

```kotlin
Modifier.semantics(
    mergeDescendants: Boolean,
    properties: SemanticsPropertyReceiver.() -> Unit
)
```
Add semantics key/value pairs to the layout node, for use in testing, accessibility, etc.

---

### clearAndSetSemantics
**Scope:** Any

```kotlin
Modifier.clearAndSetSemantics(
    properties: SemanticsPropertyReceiver.() -> Unit
)
```
Clears the semantics of all the descendant nodes and sets new semantics.

---

### testTag
**Scope:** Any

```kotlin
Modifier.testTag(tag: String)
```
Applies a tag to allow modified element to be found in tests.

---

## Transformations

### rotate
**Scope:** Any

```kotlin
Modifier.rotate(degrees: Float)
```
Sets the degrees the view is rotated around the center of the composable.

---

### scale
**Scope:** Any

```kotlin
Modifier.scale(scale: Float)
Modifier.scale(scaleX: Float, scaleY: Float)
```
Scale the contents uniformly or along horizontal and vertical axis.

---

## Position

### offset
**Scope:** Any

```kotlin
Modifier.offset(x: Dp, y: Dp)
Modifier.offset(offset: Density.() -> IntOffset)
```
Offset the content by (x dp, y dp) or by the result of the offset lambda.

---

### absoluteOffset
**Scope:** Any

```kotlin
Modifier.absoluteOffset(x: Dp, y: Dp)
Modifier.absoluteOffset(offset: Density.() -> IntOffset)
```
Offset the content (does not consider layout direction).

---

## Graphics

### graphicsLayer
**Scope:** Any

```kotlin
Modifier.graphicsLayer(block: GraphicsLayerScope.() -> Unit)
```
A Modifier.Node that makes content draw into a draw layer.

---

## Layout

### layout
**Scope:** Any

```kotlin
Modifier.layout(
    measure: MeasureScope.(Measurable, Constraints) -> MeasureResult
)
```
Creates a LayoutModifier that allows changing how the wrapped element is measured and laid out.

---

### onGloballyPositioned
**Scope:** Any

```kotlin
Modifier.onGloballyPositioned(
    onGloballyPositioned: (LayoutCoordinates) -> Unit
)
```
Invoke onGloballyPositioned with the LayoutCoordinates of the element when the global position of the content may have changed.

---

### onSizeChanged
**Scope:** Any

```kotlin
Modifier.onSizeChanged(onSizeChanged: (IntSize) -> Unit)
```
Invoked with the size of the modified Compose UI element when the element is first measured or when the size of the element changes.

---

## Keyboard

### onKeyEvent
**Scope:** Any

```kotlin
Modifier.onKeyEvent(onKeyEvent: (KeyEvent) -> Boolean)
```
Adding this modifier to the modifier parameter of a component will allow it to intercept hardware key events when it (or one of its children) is focused.

---

### onPreviewKeyEvent
**Scope:** Any

```kotlin
Modifier.onPreviewKeyEvent(
    onPreviewKeyEvent: (KeyEvent) -> Boolean
)
```
Adding this modifier will allow it to intercept hardware key events before they are sent to children.

---

## Other Common Modifiers

### clickable + indication
Use `indication` parameter in clickable to customize visual feedback.

### hoverable
Make elements respond to hover events.

### indication
Draw visual effects for interactions.

### composed
Create just-in-time composed modifiers.

### then
Chain modifiers together.

---

**Note:** This is a reformatted version for better readability. Refer to official Jetpack Compose documentation for complete and up-to-date information.