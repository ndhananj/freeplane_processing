Below is how the XML in **freeplaneFunctions.mm** maps onto the visual elements you see in the screenshot:

---

## 1. The Central (“Root”) Node

```xml
<node TEXT="Basic Freeplane&#xa;Functions"
      BACKGROUND_COLOR="#00ff99">
  <icon BUILTIN="bee"/>
  <font BOLD="true"/>
  …
</node>
```

* **Text & Color**: Renders as the large turquoise bubble labeled
  “Basic Freeplane
  Functions”&#x20;
* **Icon**: The bee icon next to it comes from `<icon BUILTIN="bee"/>` .
* **Font Weight**: Bold title as per `<font BOLD="true"/>` .

---

## 2. Left‐Hand Branches

### • **Summary node (accolade)**

```xml
<node POSITION="left" …>
  <hook NAME="SummaryNode"/>
  <node TEXT="Summary node&#xa;(accolade)" …>
    <font BOLD="true"/>
    …
    <edge COLOR="#ff00ff" WIDTH="3"/>
  </node>
</node>
```

* Shows the pink curly‐brace “accolade” around “Summary node (accolade)” .

### • **Format node core**

```xml
<node TEXT="Format node core" POSITION="left" …>
  <richcontent TYPE="NOTE">…link to Formatting and styling…</richcontent>
  …
  <node TEXT="Font"> … </node>
  <node TEXT="Color"> … </node>
</node>
```

* Corresponds to the branch labeled “Format node core” with its child subnodes “Font” and “Color” .

#### ◦ **Font → Dialog font / Times New Roman**

Under `<node TEXT="Font">` you’ll find:

```xml
  <node TEXT="Dialog font">
    <font NAME="Dialog" SIZE="21"/>
  …
```

matching the “Dialog font” and “Times New Roman” entries in the screenshot .

---

## 3. Special & Calculations („Special“)

```xml
<node TEXT="Special" …>
  <node>…<body>Reminder (<b>Calendar</b>)</body>…</node>
  <node>…<body><b>Calculate</b> =3+4</body>…</node>
  <node ENCRYPTED_CONTENT=…>…Protect with password…</node>
</node>
```

* Renders the “Reminder (Calendar)”, the “Calculate =3+4” (with live result), and the padlock icon for “Protect with password” under the “Special” heading in the screenshot .

---

## 4. Right‐Hand Branches

### • **Below node extensions or Note**

```xml
<node POSITION="right" …>
  <node TEXT="Below node extensions or in separate window: Note" …>
    …
  </node>
  <edge COLOR="#006633" WIDTH="2"/>
  …
  <node TEXT="Node extensions">…</node>
</node>
```

* Matches the yellow “Below node extensions … Note” box and its green link to “Node extensions” .

### • **Edges formatting panel**

```xml
<node TEXT="Edges" STYLE_REF="Reference">  
  <arrowlink SHAPE="LINE" DASH="3 3" …/>
  <arrowlink SHAPE="LINE" DASH="3 3" …/>
</node>
```

* Produces the two dashed‐line previews in the light-blue “? Edges” panel, with style, width and color settings .

### • **Latest features**

```xml
<node TEXT="Latest features" POSITION="right" LINK="latestFreeplaneFeatures.mm"
      FORMAT_AS_HYPERLINK="true"
      CLOUD COLOR="#ffcccc" SHAPE="ARC">
  <font SIZE="12"/>
</node>
```

* Renders the pink oval “Latest features” on the right, hyperlinked to an external map .

---

### In short

Every `<node …>` element in the XML carries attributes for **TEXT**, **POSITION**, **STYLE** (bubble, oval, cloud), **COLORS**, **FONTS**, **ICONS** and **edges/arrowlink definitions**. Freeplane reads those tags and properties to draw exactly the map you see in the screenshot.

