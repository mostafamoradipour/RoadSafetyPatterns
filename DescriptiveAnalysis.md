<!DOCTYPE html>

<html lang="en">
<head><meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<title>DescriptiveAnalysis</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<style type="text/css">
    pre { line-height: 125%; }
td.linenos .normal { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
span.linenos { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
td.linenos .special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .pm { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation.Marker */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>
<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/* tiny scrollbar */

.jp-scrollbar-tiny {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
  scrollbar-width: thin;
}

/* tiny scrollbar */

.jp-scrollbar-tiny::-webkit-scrollbar,
.jp-scrollbar-tiny::-webkit-scrollbar-corner {
  background-color: transparent;
  height: 4px;
  width: 4px;
}

.jp-scrollbar-tiny::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:horizontal {
  border-left: 0 solid transparent;
  border-right: 0 solid transparent;
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:vertical {
  border-top: 0 solid transparent;
  border-bottom: 0 solid transparent;
}

/*
 * Lumino
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
}

.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.lm-AccordionPanel[data-orientation='horizontal'] > .lm-AccordionPanel-title {
  /* Title is rotated for horizontal accordion panel using CSS */
  display: block;
  transform-origin: top left;
  transform: rotate(-90deg) translate(-100%);
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-CommandPalette-search {
  flex: 0 0 auto;
}

.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}

.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}

.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}

.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-close-icon {
  border: 1px solid transparent;
  background-color: transparent;
  position: absolute;
  z-index: 1;
  right: 3%;
  top: 0;
  bottom: 0;
  margin: auto;
  padding: 7px 0;
  display: none;
  vertical-align: middle;
  outline: 0;
  cursor: pointer;
}
.lm-close-icon:after {
  content: 'X';
  display: block;
  width: 15px;
  height: 15px;
  text-align: center;
  color: #000;
  font-weight: normal;
  font-size: 12px;
  cursor: pointer;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-DockPanel {
  z-index: 0;
}

.lm-DockPanel-widget {
  z-index: 0;
}

.lm-DockPanel-tabBar {
  z-index: 1;
}

.lm-DockPanel-handle {
  z-index: 2;
}

.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}

.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}

.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}

.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}

.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}

.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}

.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}

.lm-Menu-item {
  display: table-row;
}

.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}

.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}

.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}

.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}

.lm-MenuBar-item {
  box-sizing: border-box;
}

.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}

.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}

.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}

.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}

.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-SplitPanel-child {
  z-index: 0;
}

.lm-SplitPanel-handle {
  z-index: 1;
}

.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}

.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}

.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}

.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}

.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}

.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
  align-items: flex-end;
}

.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
  align-items: flex-end;
}

.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}

.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}

.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}

.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
  touch-action: none; /* Disable native Drag/Drop */
}

.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}

.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}

.lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing: border-box;
}

.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}

.lm-TabBar-addButton.lm-mod-hidden {
  display: none !important;
}

.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}

.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}

.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}

.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

.lm-TabBar-tabLabel .lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing: border-box;
  background: inherit;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-TabPanel-tabBar {
  z-index: 1;
}

.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
}

.jp-Collapse-header {
  padding: 1px 12px;
  background-color: var(--jp-layout-color1);
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  align-items: center;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  text-transform: uppercase;
  user-select: none;
}

.jp-Collapser-icon {
  height: 16px;
}

.jp-Collapse-header-collapsed .jp-Collapser-icon {
  transform: rotate(-90deg);
  margin: auto 0;
}

.jp-Collapser-title {
  line-height: 25px;
}

.jp-Collapse-contents {
  padding: 0 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add-above: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzEzN18xOTQ5MikiPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGQ9Ik00Ljc1IDQuOTMwNjZINi42MjVWNi44MDU2NkM2LjYyNSA3LjAxMTkxIDYuNzkzNzUgNy4xODA2NiA3IDcuMTgwNjZDNy4yMDYyNSA3LjE4MDY2IDcuMzc1IDcuMDExOTEgNy4zNzUgNi44MDU2NlY0LjkzMDY2SDkuMjVDOS40NTYyNSA0LjkzMDY2IDkuNjI1IDQuNzYxOTEgOS42MjUgNC41NTU2NkM5LjYyNSA0LjM0OTQxIDkuNDU2MjUgNC4xODA2NiA5LjI1IDQuMTgwNjZINy4zNzVWMi4zMDU2NkM3LjM3NSAyLjA5OTQxIDcuMjA2MjUgMS45MzA2NiA3IDEuOTMwNjZDNi43OTM3NSAxLjkzMDY2IDYuNjI1IDIuMDk5NDEgNi42MjUgMi4zMDU2NlY0LjE4MDY2SDQuNzVDNC41NDM3NSA0LjE4MDY2IDQuMzc1IDQuMzQ5NDEgNC4zNzUgNC41NTU2NkM0LjM3NSA0Ljc2MTkxIDQuNTQzNzUgNC45MzA2NiA0Ljc1IDQuOTMwNjZaIiBmaWxsPSIjNjE2MTYxIiBzdHJva2U9IiM2MTYxNjEiIHN0cm9rZS13aWR0aD0iMC43Ii8+CjwvZz4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTExLjUgOS41VjExLjVMMi41IDExLjVWOS41TDExLjUgOS41Wk0xMiA4QzEyLjU1MjMgOCAxMyA4LjQ0NzcyIDEzIDlWMTJDMTMgMTIuNTUyMyAxMi41NTIzIDEzIDEyIDEzTDIgMTNDMS40NDc3MiAxMyAxIDEyLjU1MjMgMSAxMlY5QzEgOC40NDc3MiAxLjQ0NzcxIDggMiA4TDEyIDhaIiBmaWxsPSIjNjE2MTYxIi8+CjxkZWZzPgo8Y2xpcFBhdGggaWQ9ImNsaXAwXzEzN18xOTQ5MiI+CjxyZWN0IGNsYXNzPSJqcC1pY29uMyIgd2lkdGg9IjYiIGhlaWdodD0iNiIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0ibWF0cml4KC0xIDAgMCAxIDEwIDEuNTU1NjYpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==);
  --jp-icon-add-below: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzEzN18xOTQ5OCkiPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGQ9Ik05LjI1IDEwLjA2OTNMNy4zNzUgMTAuMDY5M0w3LjM3NSA4LjE5NDM0QzcuMzc1IDcuOTg4MDkgNy4yMDYyNSA3LjgxOTM0IDcgNy44MTkzNEM2Ljc5Mzc1IDcuODE5MzQgNi42MjUgNy45ODgwOSA2LjYyNSA4LjE5NDM0TDYuNjI1IDEwLjA2OTNMNC43NSAxMC4wNjkzQzQuNTQzNzUgMTAuMDY5MyA0LjM3NSAxMC4yMzgxIDQuMzc1IDEwLjQ0NDNDNC4zNzUgMTAuNjUwNiA0LjU0Mzc1IDEwLjgxOTMgNC43NSAxMC44MTkzTDYuNjI1IDEwLjgxOTNMNi42MjUgMTIuNjk0M0M2LjYyNSAxMi45MDA2IDYuNzkzNzUgMTMuMDY5MyA3IDEzLjA2OTNDNy4yMDYyNSAxMy4wNjkzIDcuMzc1IDEyLjkwMDYgNy4zNzUgMTIuNjk0M0w3LjM3NSAxMC44MTkzTDkuMjUgMTAuODE5M0M5LjQ1NjI1IDEwLjgxOTMgOS42MjUgMTAuNjUwNiA5LjYyNSAxMC40NDQzQzkuNjI1IDEwLjIzODEgOS40NTYyNSAxMC4wNjkzIDkuMjUgMTAuMDY5M1oiIGZpbGw9IiM2MTYxNjEiIHN0cm9rZT0iIzYxNjE2MSIgc3Ryb2tlLXdpZHRoPSIwLjciLz4KPC9nPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGZpbGwtcnVsZT0iZXZlbm9kZCIgY2xpcC1ydWxlPSJldmVub2RkIiBkPSJNMi41IDUuNUwyLjUgMy41TDExLjUgMy41TDExLjUgNS41TDIuNSA1LjVaTTIgN0MxLjQ0NzcyIDcgMSA2LjU1MjI4IDEgNkwxIDNDMSAyLjQ0NzcyIDEuNDQ3NzIgMiAyIDJMMTIgMkMxMi41NTIzIDIgMTMgMi40NDc3MiAxMyAzTDEzIDZDMTMgNi41NTIyOSAxMi41NTIzIDcgMTIgN0wyIDdaIiBmaWxsPSIjNjE2MTYxIi8+CjxkZWZzPgo8Y2xpcFBhdGggaWQ9ImNsaXAwXzEzN18xOTQ5OCI+CjxyZWN0IGNsYXNzPSJqcC1pY29uMyIgd2lkdGg9IjYiIGhlaWdodD0iNiIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0ibWF0cml4KDEgMS43NDg0NmUtMDcgMS43NDg0NmUtMDcgLTEgNCAxMy40NDQzKSIvPgo8L2NsaXBQYXRoPgo8L2RlZnM+Cjwvc3ZnPgo=);
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bell: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE2IDE2IiB2ZXJzaW9uPSIxLjEiPgogICA8cGF0aCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMzMzMzMzIgogICAgICBkPSJtOCAwLjI5Yy0xLjQgMC0yLjcgMC43My0zLjYgMS44LTEuMiAxLjUtMS40IDMuNC0xLjUgNS4yLTAuMTggMi4yLTAuNDQgNC0yLjMgNS4zbDAuMjggMS4zaDVjMC4wMjYgMC42NiAwLjMyIDEuMSAwLjcxIDEuNSAwLjg0IDAuNjEgMiAwLjYxIDIuOCAwIDAuNTItMC40IDAuNi0xIDAuNzEtMS41aDVsMC4yOC0xLjNjLTEuOS0wLjk3LTIuMi0zLjMtMi4zLTUuMy0wLjEzLTEuOC0wLjI2LTMuNy0xLjUtNS4yLTAuODUtMS0yLjItMS44LTMuNi0xLjh6bTAgMS40YzAuODggMCAxLjkgMC41NSAyLjUgMS4zIDAuODggMS4xIDEuMSAyLjcgMS4yIDQuNCAwLjEzIDEuNyAwLjIzIDMuNiAxLjMgNS4yaC0xMGMxLjEtMS42IDEuMi0zLjQgMS4zLTUuMiAwLjEzLTEuNyAwLjMtMy4zIDEuMi00LjQgMC41OS0wLjcyIDEuNi0xLjMgMi41LTEuM3ptLTAuNzQgMTJoMS41Yy0wLjAwMTUgMC4yOCAwLjAxNSAwLjc5LTAuNzQgMC43OS0wLjczIDAuMDAxNi0wLjcyLTAuNTMtMC43NC0wLjc5eiIgLz4KPC9zdmc+Cg==);
  --jp-icon-bug-dot: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiPgogICAgICAgIDxwYXRoIGZpbGwtcnVsZT0iZXZlbm9kZCIgY2xpcC1ydWxlPSJldmVub2RkIiBkPSJNMTcuMTkgOEgyMFYxMEgxNy45MUMxNy45NiAxMC4zMyAxOCAxMC42NiAxOCAxMVYxMkgyMFYxNEgxOC41SDE4VjE0LjAyNzVDMTUuNzUgMTQuMjc2MiAxNCAxNi4xODM3IDE0IDE4LjVDMTQgMTkuMjA4IDE0LjE2MzUgMTkuODc3OSAxNC40NTQ5IDIwLjQ3MzlDMTMuNzA2MyAyMC44MTE3IDEyLjg3NTcgMjEgMTIgMjFDOS43OCAyMSA3Ljg1IDE5Ljc5IDYuODEgMThINFYxNkg2LjA5QzYuMDQgMTUuNjcgNiAxNS4zNCA2IDE1VjE0SDRWMTJINlYxMUM2IDEwLjY2IDYuMDQgMTAuMzMgNi4wOSAxMEg0VjhINi44MUM3LjI2IDcuMjIgNy44OCA2LjU1IDguNjIgNi4wNEw3IDQuNDFMOC40MSAzTDEwLjU5IDUuMTdDMTEuMDQgNS4wNiAxMS41MSA1IDEyIDVDMTIuNDkgNSAxMi45NiA1LjA2IDEzLjQyIDUuMTdMMTUuNTkgM0wxNyA0LjQxTDE1LjM3IDYuMDRDMTYuMTIgNi41NSAxNi43NCA3LjIyIDE3LjE5IDhaTTEwIDE2SDE0VjE0SDEwVjE2Wk0xMCAxMkgxNFYxMEgxMFYxMloiIGZpbGw9IiM2MTYxNjEiLz4KICAgICAgICA8cGF0aCBkPSJNMjIgMTguNUMyMiAyMC40MzMgMjAuNDMzIDIyIDE4LjUgMjJDMTYuNTY3IDIyIDE1IDIwLjQzMyAxNSAxOC41QzE1IDE2LjU2NyAxNi41NjcgMTUgMTguNSAxNUMyMC40MzMgMTUgMjIgMTYuNTY3IDIyIDE4LjVaIiBmaWxsPSIjNjE2MTYxIi8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yMCA4aC0yLjgxYy0uNDUtLjc4LTEuMDctMS40NS0xLjgyLTEuOTZMMTcgNC40MSAxNS41OSAzbC0yLjE3IDIuMTdDMTIuOTYgNS4wNiAxMi40OSA1IDEyIDVjLS40OSAwLS45Ni4wNi0xLjQxLjE3TDguNDEgMyA3IDQuNDFsMS42MiAxLjYzQzcuODggNi41NSA3LjI2IDcuMjIgNi44MSA4SDR2MmgyLjA5Yy0uMDUuMzMtLjA5LjY2LS4wOSAxdjFINHYyaDJ2MWMwIC4zNC4wNC42Ny4wOSAxSDR2MmgyLjgxYzEuMDQgMS43OSAyLjk3IDMgNS4xOSAzczQuMTUtMS4yMSA1LjE5LTNIMjB2LTJoLTIuMDljLjA1LS4zMy4wOS0uNjYuMDktMXYtMWgydi0yaC0ydi0xYzAtLjM0LS4wNC0uNjctLjA5LTFIMjBWOHptLTYgOGgtNHYtMmg0djJ6bTAtNGgtNHYtMmg0djJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik05IDE2LjE3TDQuODMgMTJsLTEuNDIgMS40MUw5IDE5IDIxIDdsLTEuNDEtMS40MXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBzaGFwZS1yZW5kZXJpbmc9Imdlb21ldHJpY1ByZWNpc2lvbiI+CiAgICA8cGF0aCBkPSJNNi41OSwzLjQxTDIsOEw2LjU5LDEyLjZMOCwxMS4xOEw0LjgyLDhMOCw0LjgyTDYuNTksMy40MU0xMi40MSwzLjQxTDExLDQuODJMMTQuMTgsOEwxMSwxMS4xOEwxMi40MSwxMi42TDE3LDhMMTIuNDEsMy40MU0yMS41OSwxMS41OUwxMy41LDE5LjY4TDkuODMsMTZMOC40MiwxNy40MUwxMy41LDIyLjVMMjMsMTNMMjEuNTksMTEuNTlaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTExLjQgMTguNkw2LjggMTRMMTEuNCA5LjRMMTAgOEw0IDE0TDEwIDIwTDExLjQgMTguNlpNMTYuNiAxOC42TDIxLjIgMTRMMTYuNiA5LjRMMTggOEwyNCAxNEwxOCAyMEwxNi42IDE4LjZWMTguNloiLz4KCTwvZz4KPC9zdmc+Cg==);
  --jp-icon-collapse-all: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTggMmMxIDAgMTEgMCAxMiAwczIgMSAyIDJjMCAxIDAgMTEgMCAxMnMwIDItMiAyQzIwIDE0IDIwIDQgMjAgNFMxMCA0IDYgNGMwLTIgMS0yIDItMnoiIC8+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTE4IDhjMC0xLTEtMi0yLTJTNSA2IDQgNnMtMiAxLTIgMmMwIDEgMCAxMSAwIDEyczEgMiAyIDJjMSAwIDExIDAgMTIgMHMyLTEgMi0yYzAtMSAwLTExIDAtMTJ6bS0yIDB2MTJINFY4eiIgLz4KICAgICAgICA8cGF0aCBkPSJNNiAxM3YyaDh2LTJ6IiAvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1jb25zb2xlLWljb24tYmFja2dyb3VuZC1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtY29uc29sZS1pY29uLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIj4KICAgIDxwYXRoIGQ9Ik0xMDUgMTI3LjNoNDB2MTIuOGgtNDB6TTUxLjEgNzdMNzQgOTkuOWwtMjMuMyAyMy4zIDEwLjUgMTAuNSAyMy4zLTIzLjNMOTUgOTkuOSA4NC41IDg5LjQgNjEuNiA2Ni41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copyright: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDI0IDI0IiBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCI+CiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0xMS44OCw5LjE0YzEuMjgsMC4wNiwxLjYxLDEuMTUsMS42MywxLjY2aDEuNzljLTAuMDgtMS45OC0xLjQ5LTMuMTktMy40NS0zLjE5QzkuNjQsNy42MSw4LDksOCwxMi4xNCBjMCwxLjk0LDAuOTMsNC4yNCwzLjg0LDQuMjRjMi4yMiwwLDMuNDEtMS42NSwzLjQ0LTIuOTVoLTEuNzljLTAuMDMsMC41OS0wLjQ1LDEuMzgtMS42MywxLjQ0QzEwLjU1LDE0LjgzLDEwLDEzLjgxLDEwLDEyLjE0IEMxMCw5LjI1LDExLjI4LDkuMTYsMTEuODgsOS4xNHogTTEyLDJDNi40OCwyLDIsNi40OCwyLDEyczQuNDgsMTAsMTAsMTBzMTAtNC40OCwxMC0xMFMxNy41MiwyLDEyLDJ6IE0xMiwyMGMtNC40MSwwLTgtMy41OS04LTggczMuNTktOCw4LThzOCwzLjU5LDgsOFMxNi40MSwyMCwxMiwyMHoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-delete: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2cHgiIGhlaWdodD0iMTZweCI+CiAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIiAvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjI2MjYyIiBkPSJNNiAxOWMwIDEuMS45IDIgMiAyaDhjMS4xIDAgMi0uOSAyLTJWN0g2djEyek0xOSA0aC0zLjVsLTEtMWgtNWwtMSAxSDV2MmgxNFY0eiIgLz4KPC9zdmc+Cg==);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-duplicate: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTIuNzk5OTggMC44NzVIOC44OTU4MkM5LjIwMDYxIDAuODc1IDkuNDQ5OTggMS4xMzkxNCA5LjQ0OTk4IDEuNDYxOThDOS40NDk5OCAxLjc4NDgyIDkuMjAwNjEgMi4wNDg5NiA4Ljg5NTgyIDIuMDQ4OTZIMy4zNTQxNUMzLjA0OTM2IDIuMDQ4OTYgMi43OTk5OCAyLjMxMzEgMi43OTk5OCAyLjYzNTk0VjkuNjc5NjlDMi43OTk5OCAxMC4wMDI1IDIuNTUwNjEgMTAuMjY2NyAyLjI0NTgyIDEwLjI2NjdDMS45NDEwMyAxMC4yNjY3IDEuNjkxNjUgMTAuMDAyNSAxLjY5MTY1IDkuNjc5NjlWMi4wNDg5NkMxLjY5MTY1IDEuNDAzMjggMi4xOTA0IDAuODc1IDIuNzk5OTggMC44NzVaTTUuMzY2NjUgMTEuOVY0LjU1SDExLjA4MzNWMTEuOUg1LjM2NjY1Wk00LjE0MTY1IDQuMTQxNjdDNC4xNDE2NSAzLjY5MDYzIDQuNTA3MjggMy4zMjUgNC45NTgzMiAzLjMyNUgxMS40OTE3QzExLjk0MjcgMy4zMjUgMTIuMzA4MyAzLjY5MDYzIDEyLjMwODMgNC4xNDE2N1YxMi4zMDgzQzEyLjMwODMgMTIuNzU5NCAxMS45NDI3IDEzLjEyNSAxMS40OTE3IDEzLjEyNUg0Ljk1ODMyQzQuNTA3MjggMTMuMTI1IDQuMTQxNjUgMTIuNzU5NCA0LjE0MTY1IDEyLjMwODNWNC4xNDE2N1oiIGZpbGw9IiM2MTYxNjEiLz4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNOS40MzU3NCA4LjI2NTA3SDguMzY0MzFWOS4zMzY1QzguMzY0MzEgOS40NTQzNSA4LjI2Nzg4IDkuNTUwNzggOC4xNTAwMiA5LjU1MDc4QzguMDMyMTcgOS41NTA3OCA3LjkzNTc0IDkuNDU0MzUgNy45MzU3NCA5LjMzNjVWOC4yNjUwN0g2Ljg2NDMxQzYuNzQ2NDUgOC4yNjUwNyA2LjY1MDAyIDguMTY4NjQgNi42NTAwMiA4LjA1MDc4QzYuNjUwMDIgNy45MzI5MiA2Ljc0NjQ1IDcuODM2NSA2Ljg2NDMxIDcuODM2NUg3LjkzNTc0VjYuNzY1MDdDNy45MzU3NCA2LjY0NzIxIDguMDMyMTcgNi41NTA3OCA4LjE1MDAyIDYuNTUwNzhDOC4yNjc4OCA2LjU1MDc4IDguMzY0MzEgNi42NDcyMSA4LjM2NDMxIDYuNzY1MDdWNy44MzY1SDkuNDM1NzRDOS41NTM2IDcuODM2NSA5LjY1MDAyIDcuOTMyOTIgOS42NTAwMiA4LjA1MDc4QzkuNjUwMDIgOC4xNjg2NCA5LjU1MzYgOC4yNjUwNyA5LjQzNTc0IDguMjY1MDdaIiBmaWxsPSIjNjE2MTYxIiBzdHJva2U9IiM2MTYxNjEiIHN0cm9rZS13aWR0aD0iMC41Ii8+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-error: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjE5IiByPSIyIi8+PHBhdGggZD0iTTEwIDNoNHYxMmgtNHoiLz48L2c+CjxwYXRoIGZpbGw9Im5vbmUiIGQ9Ik0wIDBoMjR2MjRIMHoiLz4KPC9zdmc+Cg==);
  --jp-icon-expand-all: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTggMmMxIDAgMTEgMCAxMiAwczIgMSAyIDJjMCAxIDAgMTEgMCAxMnMwIDItMiAyQzIwIDE0IDIwIDQgMjAgNFMxMCA0IDYgNGMwLTIgMS0yIDItMnoiIC8+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTE4IDhjMC0xLTEtMi0yLTJTNSA2IDQgNnMtMiAxLTIgMmMwIDEgMCAxMSAwIDEyczEgMiAyIDJjMSAwIDExIDAgMTIgMHMyLTEgMi0yYzAtMSAwLTExIDAtMTJ6bS0yIDB2MTJINFY4eiIgLz4KICAgICAgICA8cGF0aCBkPSJNMTEgMTBIOXYzSDZ2MmgzdjNoMnYtM2gzdi0yaC0zeiIgLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-dot: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTE0LDEyVjE5Ljg4QzE0LjA0LDIwLjE4IDEzLjk0LDIwLjUgMTMuNzEsMjAuNzFDMTMuMzIsMjEuMSAxMi42OSwyMS4xIDEyLjMsMjAuNzFMMTAuMjksMTguN0MxMC4wNiwxOC40NyA5Ljk2LDE4LjE2IDEwLDE3Ljg3VjEySDkuOTdMNC4yMSw0LjYyQzMuODcsNC4xOSAzLjk1LDMuNTYgNC4zOCwzLjIyQzQuNTcsMy4wOCA0Ljc4LDMgNSwzVjNIMTlWM0MxOS4yMiwzIDE5LjQzLDMuMDggMTkuNjIsMy4yMkMyMC4wNSwzLjU2IDIwLjEzLDQuMTkgMTkuNzksNC42MkwxNC4wMywxMkgxNFoiIC8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWRvdCIgZmlsbD0iI0ZGRiI+CiAgICA8Y2lyY2xlIGN4PSIxOCIgY3k9IjE3IiByPSIzIj48L2NpcmNsZT4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-filter: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTE0LDEyVjE5Ljg4QzE0LjA0LDIwLjE4IDEzLjk0LDIwLjUgMTMuNzEsMjAuNzFDMTMuMzIsMjEuMSAxMi42OSwyMS4xIDEyLjMsMjAuNzFMMTAuMjksMTguN0MxMC4wNiwxOC40NyA5Ljk2LDE4LjE2IDEwLDE3Ljg3VjEySDkuOTdMNC4yMSw0LjYyQzMuODcsNC4xOSAzLjk1LDMuNTYgNC4zOCwzLjIyQzQuNTcsMy4wOCA0Ljc4LDMgNSwzVjNIMTlWM0MxOS4yMiwzIDE5LjQzLDMuMDggMTkuNjIsMy4yMkMyMC4wNSwzLjU2IDIwLjEzLDQuMTkgMTkuNzksNC42MkwxNC4wMywxMkgxNFoiIC8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-folder-favorite: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjRweCIgdmlld0JveD0iMCAwIDI0IDI0IiB3aWR0aD0iMjRweCIgZmlsbD0iIzAwMDAwMCI+CiAgPHBhdGggZD0iTTAgMGgyNHYyNEgwVjB6IiBmaWxsPSJub25lIi8+PHBhdGggY2xhc3M9ImpwLWljb24zIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxNjE2MSIgZD0iTTIwIDZoLThsLTItMkg0Yy0xLjEgMC0yIC45LTIgMnYxMmMwIDEuMS45IDIgMiAyaDE2YzEuMSAwIDItLjkgMi0yVjhjMC0xLjEtLjktMi0yLTJ6bS0yLjA2IDExTDE1IDE1LjI4IDEyLjA2IDE3bC43OC0zLjMzLTIuNTktMi4yNCAzLjQxLS4yOUwxNSA4bDEuMzQgMy4xNCAzLjQxLjI5LTIuNTkgMi4yNC43OCAzLjMzeiIvPgo8L3N2Zz4K);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-home: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjRweCIgdmlld0JveD0iMCAwIDI0IDI0IiB3aWR0aD0iMjRweCIgZmlsbD0iIzAwMDAwMCI+CiAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPjxwYXRoIGNsYXNzPSJqcC1pY29uMyBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xMCAyMHYtNmg0djZoNXYtOGgzTDEyIDMgMiAxMmgzdjh6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-info: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUwLjk3OCA1MC45NzgiPgoJPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KCQk8cGF0aCBkPSJNNDMuNTIsNy40NThDMzguNzExLDIuNjQ4LDMyLjMwNywwLDI1LjQ4OSwwQzE4LjY3LDAsMTIuMjY2LDIuNjQ4LDcuNDU4LDcuNDU4CgkJCWMtOS45NDMsOS45NDEtOS45NDMsMjYuMTE5LDAsMzYuMDYyYzQuODA5LDQuODA5LDExLjIxMiw3LjQ1NiwxOC4wMzEsNy40NThjMCwwLDAuMDAxLDAsMC4wMDIsMAoJCQljNi44MTYsMCwxMy4yMjEtMi42NDgsMTguMDI5LTcuNDU4YzQuODA5LTQuODA5LDcuNDU3LTExLjIxMiw3LjQ1Ny0xOC4wM0M1MC45NzcsMTguNjcsNDguMzI4LDEyLjI2Niw0My41Miw3LjQ1OHoKCQkJIE00Mi4xMDYsNDIuMTA1Yy00LjQzMiw0LjQzMS0xMC4zMzIsNi44NzItMTYuNjE1LDYuODcyaC0wLjAwMmMtNi4yODUtMC4wMDEtMTIuMTg3LTIuNDQxLTE2LjYxNy02Ljg3MgoJCQljLTkuMTYyLTkuMTYzLTkuMTYyLTI0LjA3MSwwLTMzLjIzM0MxMy4zMDMsNC40NCwxOS4yMDQsMiwyNS40ODksMmM2LjI4NCwwLDEyLjE4NiwyLjQ0LDE2LjYxNyw2Ljg3MgoJCQljNC40MzEsNC40MzEsNi44NzEsMTAuMzMyLDYuODcxLDE2LjYxN0M0OC45NzcsMzEuNzcyLDQ2LjUzNiwzNy42NzUsNDIuMTA2LDQyLjEwNXoiLz4KCQk8cGF0aCBkPSJNMjMuNTc4LDMyLjIxOGMtMC4wMjMtMS43MzQsMC4xNDMtMy4wNTksMC40OTYtMy45NzJjMC4zNTMtMC45MTMsMS4xMS0xLjk5NywyLjI3Mi0zLjI1MwoJCQljMC40NjgtMC41MzYsMC45MjMtMS4wNjIsMS4zNjctMS41NzVjMC42MjYtMC43NTMsMS4xMDQtMS40NzgsMS40MzYtMi4xNzVjMC4zMzEtMC43MDcsMC40OTUtMS41NDEsMC40OTUtMi41CgkJCWMwLTEuMDk2LTAuMjYtMi4wODgtMC43NzktMi45NzljLTAuNTY1LTAuODc5LTEuNTAxLTEuMzM2LTIuODA2LTEuMzY5Yy0xLjgwMiwwLjA1Ny0yLjk4NSwwLjY2Ny0zLjU1LDEuODMyCgkJCWMtMC4zMDEsMC41MzUtMC41MDMsMS4xNDEtMC42MDcsMS44MTRjLTAuMTM5LDAuNzA3LTAuMjA3LDEuNDMyLTAuMjA3LDIuMTc0aC0yLjkzN2MtMC4wOTEtMi4yMDgsMC40MDctNC4xMTQsMS40OTMtNS43MTkKCQkJYzEuMDYyLTEuNjQsMi44NTUtMi40ODEsNS4zNzgtMi41MjdjMi4xNiwwLjAyMywzLjg3NCwwLjYwOCw1LjE0MSwxLjc1OGMxLjI3OCwxLjE2LDEuOTI5LDIuNzY0LDEuOTUsNC44MTEKCQkJYzAsMS4xNDItMC4xMzcsMi4xMTEtMC40MSwyLjkxMWMtMC4zMDksMC44NDUtMC43MzEsMS41OTMtMS4yNjgsMi4yNDNjLTAuNDkyLDAuNjUtMS4wNjgsMS4zMTgtMS43MywyLjAwMgoJCQljLTAuNjUsMC42OTctMS4zMTMsMS40NzktMS45ODcsMi4zNDZjLTAuMjM5LDAuMzc3LTAuNDI5LDAuNzc3LTAuNTY1LDEuMTk5Yy0wLjE2LDAuOTU5LTAuMjE3LDEuOTUxLTAuMTcxLDIuOTc5CgkJCUMyNi41ODksMzIuMjE4LDIzLjU3OCwzMi4yMTgsMjMuNTc4LDMyLjIxOHogTTIzLjU3OCwzOC4yMnYtMy40ODRoMy4wNzZ2My40ODRIMjMuNTc4eiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaW5zcGVjdG9yLWljb24tY29sb3IganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtanNvbi1pY29uLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0Y5QTgyNSI+CiAgICA8cGF0aCBkPSJNMjAuMiAxMS44Yy0xLjYgMC0xLjcuNS0xLjcgMSAwIC40LjEuOS4xIDEuMy4xLjUuMS45LjEgMS4zIDAgMS43LTEuNCAyLjMtMy41IDIuM2gtLjl2LTEuOWguNWMxLjEgMCAxLjQgMCAxLjQtLjggMC0uMyAwLS42LS4xLTEgMC0uNC0uMS0uOC0uMS0xLjIgMC0xLjMgMC0xLjggMS4zLTItMS4zLS4yLTEuMy0uNy0xLjMtMiAwLS40LjEtLjguMS0xLjIuMS0uNC4xLS43LjEtMSAwLS44LS40LS43LTEuNC0uOGgtLjVWNC4xaC45YzIuMiAwIDMuNS43IDMuNSAyLjMgMCAuNC0uMS45LS4xIDEuMy0uMS41LS4xLjktLjEgMS4zIDAgLjUuMiAxIDEuNyAxdjEuOHpNMS44IDEwLjFjMS42IDAgMS43LS41IDEuNy0xIDAtLjQtLjEtLjktLjEtMS4zLS4xLS41LS4xLS45LS4xLTEuMyAwLTEuNiAxLjQtMi4zIDMuNS0yLjNoLjl2MS45aC0uNWMtMSAwLTEuNCAwLTEuNC44IDAgLjMgMCAuNi4xIDEgMCAuMi4xLjYuMSAxIDAgMS4zIDAgMS44LTEuMyAyQzYgMTEuMiA2IDExLjcgNiAxM2MwIC40LS4xLjgtLjEgMS4yLS4xLjMtLjEuNy0uMSAxIDAgLjguMy44IDEuNC44aC41djEuOWgtLjljLTIuMSAwLTMuNS0uNi0zLjUtMi4zIDAtLjQuMS0uOS4xLTEuMy4xLS41LjEtLjkuMS0xLjMgMC0uNS0uMi0xLTEuNy0xdi0xLjl6Ii8+CiAgICA8Y2lyY2xlIGN4PSIxMSIgY3k9IjEzLjgiIHI9IjIuMSIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSI4LjIiIHI9IjIuMSIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-julia: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDMyNSAzMDAiPgogIDxnIGNsYXNzPSJqcC1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjY2IzYzMzIj4KICAgIDxwYXRoIGQ9Ik0gMTUwLjg5ODQzOCAyMjUgQyAxNTAuODk4NDM4IDI2Ni40MjE4NzUgMTE3LjMyMDMxMiAzMDAgNzUuODk4NDM4IDMwMCBDIDM0LjQ3NjU2MiAzMDAgMC44OTg0MzggMjY2LjQyMTg3NSAwLjg5ODQzOCAyMjUgQyAwLjg5ODQzOCAxODMuNTc4MTI1IDM0LjQ3NjU2MiAxNTAgNzUuODk4NDM4IDE1MCBDIDExNy4zMjAzMTIgMTUwIDE1MC44OTg0MzggMTgzLjU3ODEyNSAxNTAuODk4NDM4IDIyNSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzM4OTgyNiI+CiAgICA8cGF0aCBkPSJNIDIzNy41IDc1IEMgMjM3LjUgMTE2LjQyMTg3NSAyMDMuOTIxODc1IDE1MCAxNjIuNSAxNTAgQyAxMjEuMDc4MTI1IDE1MCA4Ny41IDExNi40MjE4NzUgODcuNSA3NSBDIDg3LjUgMzMuNTc4MTI1IDEyMS4wNzgxMjUgMCAxNjIuNSAwIEMgMjAzLjkyMTg3NSAwIDIzNy41IDMzLjU3ODEyNSAyMzcuNSA3NSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzk1NThiMiI+CiAgICA8cGF0aCBkPSJNIDMyNC4xMDE1NjIgMjI1IEMgMzI0LjEwMTU2MiAyNjYuNDIxODc1IDI5MC41MjM0MzggMzAwIDI0OS4xMDE1NjIgMzAwIEMgMjA3LjY3OTY4OCAzMDAgMTc0LjEwMTU2MiAyNjYuNDIxODc1IDE3NC4xMDE1NjIgMjI1IEMgMTc0LjEwMTU2MiAxODMuNTc4MTI1IDIwNy42Nzk2ODggMTUwIDI0OS4xMDE1NjIgMTUwIEMgMjkwLjUyMzQzOCAxNTAgMzI0LjEwMTU2MiAxODMuNTc4MTI1IDMyNC4xMDE1NjIgMjI1Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgPGcgY2xhc3M9ImpwLWp1cHl0ZXItaWNvbi1jb2xvciIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgIDxnIGNsYXNzPSJqcC1qdXB5dGVyLWljb24tY29sb3IiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launch: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMzIgMzIiIHdpZHRoPSIzMiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yNiwyOEg2YTIuMDAyNywyLjAwMjcsMCwwLDEtMi0yVjZBMi4wMDI3LDIuMDAyNywwLDAsMSw2LDRIMTZWNkg2VjI2SDI2VjE2aDJWMjZBMi4wMDI3LDIuMDAyNywwLDAsMSwyNiwyOFoiLz4KICAgIDxwb2x5Z29uIHBvaW50cz0iMjAgMiAyMCA0IDI2LjU4NiA0IDE4IDEyLjU4NiAxOS40MTQgMTQgMjggNS40MTQgMjggMTIgMzAgMTIgMzAgMiAyMCAyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4K);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-move-down: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNMTIuNDcxIDcuNTI4OTlDMTIuNzYzMiA3LjIzNjg0IDEyLjc2MzIgNi43NjMxNiAxMi40NzEgNi40NzEwMVY2LjQ3MTAxQzEyLjE3OSA2LjE3OTA1IDExLjcwNTcgNi4xNzg4NCAxMS40MTM1IDYuNDcwNTRMNy43NSAxMC4xMjc1VjEuNzVDNy43NSAxLjMzNTc5IDcuNDE0MjEgMSA3IDFWMUM2LjU4NTc5IDEgNi4yNSAxLjMzNTc5IDYuMjUgMS43NVYxMC4xMjc1TDIuNTk3MjYgNi40NjgyMkMyLjMwMzM4IDYuMTczODEgMS44MjY0MSA2LjE3MzU5IDEuNTMyMjYgNi40Njc3NFY2LjQ2Nzc0QzEuMjM4MyA2Ljc2MTcgMS4yMzgzIDcuMjM4MyAxLjUzMjI2IDcuNTMyMjZMNi4yOTI4OSAxMi4yOTI5QzYuNjgzNDIgMTIuNjgzNCA3LjMxNjU4IDEyLjY4MzQgNy43MDcxMSAxMi4yOTI5TDEyLjQ3MSA3LjUyODk5WiIgZmlsbD0iIzYxNjE2MSIvPgo8L3N2Zz4K);
  --jp-icon-move-up: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNMS41Mjg5OSA2LjQ3MTAxQzEuMjM2ODQgNi43NjMxNiAxLjIzNjg0IDcuMjM2ODQgMS41Mjg5OSA3LjUyODk5VjcuNTI4OTlDMS44MjA5NSA3LjgyMDk1IDIuMjk0MjYgNy44MjExNiAyLjU4NjQ5IDcuNTI5NDZMNi4yNSAzLjg3MjVWMTIuMjVDNi4yNSAxMi42NjQyIDYuNTg1NzkgMTMgNyAxM1YxM0M3LjQxNDIxIDEzIDcuNzUgMTIuNjY0MiA3Ljc1IDEyLjI1VjMuODcyNUwxMS40MDI3IDcuNTMxNzhDMTEuNjk2NiA3LjgyNjE5IDEyLjE3MzYgNy44MjY0MSAxMi40Njc3IDcuNTMyMjZWNy41MzIyNkMxMi43NjE3IDcuMjM4MyAxMi43NjE3IDYuNzYxNyAxMi40Njc3IDYuNDY3NzRMNy43MDcxMSAxLjcwNzExQzcuMzE2NTggMS4zMTY1OCA2LjY4MzQyIDEuMzE2NTggNi4yOTI4OSAxLjcwNzExTDEuNTI4OTkgNi40NzEwMVoiIGZpbGw9IiM2MTYxNjEiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtbm90ZWJvb2staWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-numbering: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTQgMTlINlYxOS41SDVWMjAuNUg2VjIxSDRWMjJIN1YxOEg0VjE5Wk01IDEwSDZWNkg0VjdINVYxMFpNNCAxM0g1LjhMNCAxNS4xVjE2SDdWMTVINS4yTDcgMTIuOVYxMkg0VjEzWk05IDdWOUgyM1Y3SDlaTTkgMjFIMjNWMTlIOVYyMVpNOSAxNUgyM1YxM0g5VjE1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-offline-bolt: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDIuMDJjLTUuNTEgMC05Ljk4IDQuNDctOS45OCA5Ljk4czQuNDcgOS45OCA5Ljk4IDkuOTggOS45OC00LjQ3IDkuOTgtOS45OFMxNy41MSAyLjAyIDEyIDIuMDJ6TTExLjQ4IDIwdi02LjI2SDhMMTMgNHY2LjI2aDMuMzVMMTEuNDggMjB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-pdf: url(data:image/svg+xml;base64,PHN2ZwogICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyMiAyMiIgd2lkdGg9IjE2Ij4KICAgIDxwYXRoIHRyYW5zZm9ybT0icm90YXRlKDQ1KSIgY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0ZGMkEyQSIKICAgICAgIGQ9Im0gMjIuMzQ0MzY5LC0zLjAxNjM2NDIgaCA1LjYzODYwNCB2IDEuNTc5MjQzMyBoIC0zLjU0OTIyNyB2IDEuNTA4NjkyOTkgaCAzLjMzNzU3NiBWIDEuNjUwODE1NCBoIC0zLjMzNzU3NiB2IDMuNDM1MjYxMyBoIC0yLjA4OTM3NyB6IG0gLTcuMTM2NDQ0LDEuNTc5MjQzMyB2IDQuOTQzOTU0MyBoIDAuNzQ4OTIgcSAxLjI4MDc2MSwwIDEuOTUzNzAzLC0wLjYzNDk1MzUgMC42NzgzNjksLTAuNjM0OTUzNSAwLjY3ODM2OSwtMS44NDUxNjQxIDAsLTEuMjA0NzgzNTUgLTAuNjcyOTQyLC0xLjgzNDMxMDExIC0wLjY3Mjk0MiwtMC42Mjk1MjY1OSAtMS45NTkxMywtMC42Mjk1MjY1OSB6IG0gLTIuMDg5Mzc3LC0xLjU3OTI0MzMgaCAyLjIwMzM0MyBxIDEuODQ1MTY0LDAgMi43NDYwMzksMC4yNjU5MjA3IDAuOTA2MzAxLDAuMjYwNDkzNyAxLjU1MjEwOCwwLjg5MDAyMDMgMC41Njk4MywwLjU0ODEyMjMgMC44NDY2MDUsMS4yNjQ0ODAwNiAwLjI3Njc3NCwwLjcxNjM1NzgxIDAuMjc2Nzc0LDEuNjIyNjU4OTQgMCwwLjkxNzE1NTEgLTAuMjc2Nzc0LDEuNjM4OTM5OSAtMC4yNzY3NzUsMC43MTYzNTc4IC0wLjg0NjYwNSwxLjI2NDQ4IC0wLjY1MTIzNCwwLjYyOTUyNjYgLTEuNTYyOTYyLDAuODk1NDQ3MyAtMC45MTE3MjgsMC4yNjA0OTM3IC0yLjczNTE4NSwwLjI2MDQ5MzcgaCAtMi4yMDMzNDMgeiBtIC04LjE0NTg1NjUsMCBoIDMuNDY3ODIzIHEgMS41NDY2ODE2LDAgMi4zNzE1Nzg1LDAuNjg5MjIzIDAuODMwMzI0LDAuNjgzNzk2MSAwLjgzMDMyNCwxLjk1MzcwMzE0IDAsMS4yNzUzMzM5NyAtMC44MzAzMjQsMS45NjQ1NTcwNiBRIDkuOTg3MTk2MSwyLjI3NDkxNSA4LjQ0MDUxNDUsMi4yNzQ5MTUgSCA3LjA2MjA2ODQgViA1LjA4NjA3NjcgSCA0Ljk3MjY5MTUgWiBtIDIuMDg5Mzc2OSwxLjUxNDExOTkgdiAyLjI2MzAzOTQzIGggMS4xNTU5NDEgcSAwLjYwNzgxODgsMCAwLjkzODg2MjksLTAuMjkzMDU1NDcgMC4zMzEwNDQxLC0wLjI5ODQ4MjQxIDAuMzMxMDQ0MSwtMC44NDExNzc3MiAwLC0wLjU0MjY5NTMxIC0wLjMzMTA0NDEsLTAuODM1NzUwNzQgLTAuMzMxMDQ0MSwtMC4yOTMwNTU1IC0wLjkzODg2MjksLTAuMjkzMDU1NSB6IgovPgo8L3N2Zz4K);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iLTEwIC0xMCAxMzEuMTYxMzYxNjk0MzM1OTQgMTMyLjM4ODk5OTkzODk2NDg0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMzA2OTk4IiBkPSJNIDU0LjkxODc4NSw5LjE5Mjc0MjFlLTQgQyA1MC4zMzUxMzIsMC4wMjIyMTcyNyA0NS45NTc4NDYsMC40MTMxMzY5NyA0Mi4xMDYyODUsMS4wOTQ2NjkzIDMwLjc2MDA2OSwzLjA5OTE3MzEgMjguNzAwMDM2LDcuMjk0NzcxNCAyOC43MDAwMzUsMTUuMDMyMTY5IHYgMTAuMjE4NzUgaCAyNi44MTI1IHYgMy40MDYyNSBoIC0yNi44MTI1IC0xMC4wNjI1IGMgLTcuNzkyNDU5LDAgLTE0LjYxNTc1ODgsNC42ODM3MTcgLTE2Ljc0OTk5OTgsMTMuNTkzNzUgLTIuNDYxODE5OTgsMTAuMjEyOTY2IC0yLjU3MTAxNTA4LDE2LjU4NjAyMyAwLDI3LjI1IDEuOTA1OTI4Myw3LjkzNzg1MiA2LjQ1NzU0MzIsMTMuNTkzNzQ4IDE0LjI0OTk5OTgsMTMuNTkzNzUgaCA5LjIxODc1IHYgLTEyLjI1IGMgMCwtOC44NDk5MDIgNy42NTcxNDQsLTE2LjY1NjI0OCAxNi43NSwtMTYuNjU2MjUgaCAyNi43ODEyNSBjIDcuNDU0OTUxLDAgMTMuNDA2MjUzLC02LjEzODE2NCAxMy40MDYyNSwtMTMuNjI1IHYgLTI1LjUzMTI1IGMgMCwtNy4yNjYzMzg2IC02LjEyOTk4LC0xMi43MjQ3NzcxIC0xMy40MDYyNSwtMTMuOTM3NDk5NyBDIDY0LjI4MTU0OCwwLjMyNzk0Mzk3IDU5LjUwMjQzOCwtMC4wMjAzNzkwMyA1NC45MTg3ODUsOS4xOTI3NDIxZS00IFogbSAtMTQuNSw4LjIxODc1MDEyNTc5IGMgMi43Njk1NDcsMCA1LjAzMTI1LDIuMjk4NjQ1NiA1LjAzMTI1LDUuMTI0OTk5NiAtMmUtNiwyLjgxNjMzNiAtMi4yNjE3MDMsNS4wOTM3NSAtNS4wMzEyNSw1LjA5Mzc1IC0yLjc3OTQ3NiwtMWUtNiAtNS4wMzEyNSwtMi4yNzc0MTUgLTUuMDMxMjUsLTUuMDkzNzUgLTEwZS03LC0yLjgyNjM1MyAyLjI1MTc3NCwtNS4xMjQ5OTk2IDUuMDMxMjUsLTUuMTI0OTk5NiB6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2ZmZDQzYiIgZD0ibSA4NS42Mzc1MzUsMjguNjU3MTY5IHYgMTEuOTA2MjUgYyAwLDkuMjMwNzU1IC03LjgyNTg5NSwxNi45OTk5OTkgLTE2Ljc1LDE3IGggLTI2Ljc4MTI1IGMgLTcuMzM1ODMzLDAgLTEzLjQwNjI0OSw2LjI3ODQ4MyAtMTMuNDA2MjUsMTMuNjI1IHYgMjUuNTMxMjQ3IGMgMCw3LjI2NjM0NCA2LjMxODU4OCwxMS41NDAzMjQgMTMuNDA2MjUsMTMuNjI1MDA0IDguNDg3MzMxLDIuNDk1NjEgMTYuNjI2MjM3LDIuOTQ2NjMgMjYuNzgxMjUsMCA2Ljc1MDE1NSwtMS45NTQzOSAxMy40MDYyNTMsLTUuODg3NjEgMTMuNDA2MjUsLTEzLjYyNTAwNCBWIDg2LjUwMDkxOSBoIC0yNi43ODEyNSB2IC0zLjQwNjI1IGggMjYuNzgxMjUgMTMuNDA2MjU0IGMgNy43OTI0NjEsMCAxMC42OTYyNTEsLTUuNDM1NDA4IDEzLjQwNjI0MSwtMTMuNTkzNzUgMi43OTkzMywtOC4zOTg4ODYgMi42ODAyMiwtMTYuNDc1Nzc2IDAsLTI3LjI1IC0xLjkyNTc4LC03Ljc1NzQ0MSAtNS42MDM4NywtMTMuNTkzNzUgLTEzLjQwNjI0MSwtMTMuNTkzNzUgeiBtIC0xNS4wNjI1LDY0LjY1NjI1IGMgMi43Nzk0NzgsM2UtNiA1LjAzMTI1LDIuMjc3NDE3IDUuMDMxMjUsNS4wOTM3NDcgLTJlLTYsMi44MjYzNTQgLTIuMjUxNzc1LDUuMTI1MDA0IC01LjAzMTI1LDUuMTI1MDA0IC0yLjc2OTU1LDAgLTUuMDMxMjUsLTIuMjk4NjUgLTUuMDMxMjUsLTUuMTI1MDA0IDJlLTYsLTIuODE2MzMgMi4yNjE2OTcsLTUuMDkzNzQ3IDUuMDMxMjUsLTUuMDkzNzQ3IHoiLz4KPC9zdmc+Cg==);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-redo: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTE4LjQgMTAuNkMxNi41NSA4Ljk5IDE0LjE1IDggMTEuNSA4Yy00LjY1IDAtOC41OCAzLjAzLTkuOTYgNy4yMkwzLjkgMTZjMS4wNS0zLjE5IDQuMDUtNS41IDcuNi01LjUgMS45NSAwIDMuNzMuNzIgNS4xMiAxLjg4TDEzIDE2aDlWN2wtMy42IDMuNnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-share: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTSAxOCAyIEMgMTYuMzU0OTkgMiAxNSAzLjM1NDk5MDQgMTUgNSBDIDE1IDUuMTkwOTUyOSAxNS4wMjE3OTEgNS4zNzcxMjI0IDE1LjA1NjY0MSA1LjU1ODU5MzggTCA3LjkyMTg3NSA5LjcyMDcwMzEgQyA3LjM5ODUzOTkgOS4yNzc4NTM5IDYuNzMyMDc3MSA5IDYgOSBDIDQuMzU0OTkwNCA5IDMgMTAuMzU0OTkgMyAxMiBDIDMgMTMuNjQ1MDEgNC4zNTQ5OTA0IDE1IDYgMTUgQyA2LjczMjA3NzEgMTUgNy4zOTg1Mzk5IDE0LjcyMjE0NiA3LjkyMTg3NSAxNC4yNzkyOTcgTCAxNS4wNTY2NDEgMTguNDM5NDUzIEMgMTUuMDIxNTU1IDE4LjYyMTUxNCAxNSAxOC44MDgzODYgMTUgMTkgQyAxNSAyMC42NDUwMSAxNi4zNTQ5OSAyMiAxOCAyMiBDIDE5LjY0NTAxIDIyIDIxIDIwLjY0NTAxIDIxIDE5IEMgMjEgMTcuMzU0OTkgMTkuNjQ1MDEgMTYgMTggMTYgQyAxNy4yNjc0OCAxNiAxNi42MDE1OTMgMTYuMjc5MzI4IDE2LjA3ODEyNSAxNi43MjI2NTYgTCA4Ljk0MzM1OTQgMTIuNTU4NTk0IEMgOC45NzgyMDk1IDEyLjM3NzEyMiA5IDEyLjE5MDk1MyA5IDEyIEMgOSAxMS44MDkwNDcgOC45NzgyMDk1IDExLjYyMjg3OCA4Ljk0MzM1OTQgMTEuNDQxNDA2IEwgMTYuMDc4MTI1IDcuMjc5Mjk2OSBDIDE2LjYwMTQ2IDcuNzIyMTQ2MSAxNy4yNjc5MjMgOCAxOCA4IEMgMTkuNjQ1MDEgOCAyMSA2LjY0NTAwOTYgMjEgNSBDIDIxIDMuMzU0OTkwNCAxOS42NDUwMSAyIDE4IDIgeiBNIDE4IDQgQyAxOC41NjQxMjkgNCAxOSA0LjQzNTg3MDYgMTkgNSBDIDE5IDUuNTY0MTI5NCAxOC41NjQxMjkgNiAxOCA2IEMgMTcuNDM1ODcxIDYgMTcgNS41NjQxMjk0IDE3IDUgQyAxNyA0LjQzNTg3MDYgMTcuNDM1ODcxIDQgMTggNCB6IE0gNiAxMSBDIDYuNTY0MTI5NCAxMSA3IDExLjQzNTg3MSA3IDEyIEMgNyAxMi41NjQxMjkgNi41NjQxMjk0IDEzIDYgMTMgQyA1LjQzNTg3MDYgMTMgNSAxMi41NjQxMjkgNSAxMiBDIDUgMTEuNDM1ODcxIDUuNDM1ODcwNiAxMSA2IDExIHogTSAxOCAxOCBDIDE4LjU2NDEyOSAxOCAxOSAxOC40MzU4NzEgMTkgMTkgQyAxOSAxOS41NjQxMjkgMTguNTY0MTI5IDIwIDE4IDIwIEMgMTcuNDM1ODcxIDIwIDE3IDE5LjU2NDEyOSAxNyAxOSBDIDE3IDE4LjQzNTg3MSAxNy40MzU4NzEgMTggMTggMTggeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-table-rows: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMSw4SDNWNGgxOFY4eiBNMjEsMTBIM3Y0aDE4VjEweiBNMjEsMTZIM3Y0aDE4VjE2eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-tag: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjgiIGhlaWdodD0iMjgiIHZpZXdCb3g9IjAgMCA0MyAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTI4LjgzMzIgMTIuMzM0TDMyLjk5OTggMTYuNTAwN0wzNy4xNjY1IDEyLjMzNEgyOC44MzMyWiIvPgoJCTxwYXRoIGQ9Ik0xNi4yMDk1IDIxLjYxMDRDMTUuNjg3MyAyMi4xMjk5IDE0Ljg0NDMgMjIuMTI5OSAxNC4zMjQ4IDIxLjYxMDRMNi45ODI5IDE0LjcyNDVDNi41NzI0IDE0LjMzOTQgNi4wODMxMyAxMy42MDk4IDYuMDQ3ODYgMTMuMDQ4MkM1Ljk1MzQ3IDExLjUyODggNi4wMjAwMiA4LjYxOTQ0IDYuMDY2MjEgNy4wNzY5NUM2LjA4MjgxIDYuNTE0NzcgNi41NTU0OCA2LjA0MzQ3IDcuMTE4MDQgNi4wMzA1NUM5LjA4ODYzIDUuOTg0NzMgMTMuMjYzOCA1LjkzNTc5IDEzLjY1MTggNi4zMjQyNUwyMS43MzY5IDEzLjYzOUMyMi4yNTYgMTQuMTU4NSAyMS43ODUxIDE1LjQ3MjQgMjEuMjYyIDE1Ljk5NDZMMTYuMjA5NSAyMS42MTA0Wk05Ljc3NTg1IDguMjY1QzkuMzM1NTEgNy44MjU2NiA4LjYyMzUxIDcuODI1NjYgOC4xODI4IDguMjY1QzcuNzQzNDYgOC43MDU3MSA3Ljc0MzQ2IDkuNDE3MzMgOC4xODI4IDkuODU2NjdDOC42MjM4MiAxMC4yOTY0IDkuMzM1ODIgMTAuMjk2NCA5Ljc3NTg1IDkuODU2NjdDMTAuMjE1NiA5LjQxNzMzIDEwLjIxNTYgOC43MDUzMyA5Ljc3NTg1IDguMjY1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtdGVybWluYWwtaWNvbi1iYWNrZ3JvdW5kLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZSIgd2lkdGg9IjIwIiBoZWlnaHQ9IjIwIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyIDIpIiBmaWxsPSIjMzMzMzMzIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtdGVybWluYWwtaWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUtaW52ZXJzZSIgZD0iTTUuMDU2NjQgOC43NjE3MkM1LjA1NjY0IDguNTk3NjYgNS4wMzEyNSA4LjQ1MzEyIDQuOTgwNDcgOC4zMjgxMkM0LjkzMzU5IDguMTk5MjIgNC44NTU0NyA4LjA4MjAzIDQuNzQ2MDkgNy45NzY1NkM0LjY0MDYyIDcuODcxMDkgNC41IDcuNzc1MzkgNC4zMjQyMiA3LjY4OTQ1QzQuMTUyMzQgNy41OTk2MSAzLjk0MzM2IDcuNTExNzIgMy42OTcyNyA3LjQyNTc4QzMuMzAyNzMgNy4yODUxNiAyLjk0MzM2IDcuMTM2NzIgMi42MTkxNCA2Ljk4MDQ3QzIuMjk0OTIgNi44MjQyMiAyLjAxNzU4IDYuNjQyNTggMS43ODcxMSA2LjQzNTU1QzEuNTYwNTUgNi4yMjg1MiAxLjM4NDc3IDUuOTg4MjggMS4yNTk3NyA1LjcxNDg0QzEuMTM0NzcgNS40Mzc1IDEuMDcyMjcgNS4xMDkzOCAxLjA3MjI3IDQuNzMwNDdDMS4wNzIyNyA0LjM5ODQ0IDEuMTI4OTEgNC4wOTU3IDEuMjQyMTkgMy44MjIyN0MxLjM1NTQ3IDMuNTQ0OTIgMS41MTU2MiAzLjMwNDY5IDEuNzIyNjYgMy4xMDE1NkMxLjkyOTY5IDIuODk4NDQgMi4xNzk2OSAyLjczNDM3IDIuNDcyNjYgMi42MDkzOEMyLjc2NTYyIDIuNDg0MzggMy4wOTE4IDIuNDA0MyAzLjQ1MTE3IDIuMzY5MTRWMS4xMDkzOEg0LjM4ODY3VjIuMzgwODZDNC43NDAyMyAyLjQyNzczIDUuMDU2NjQgMi41MjM0NCA1LjMzNzg5IDIuNjY3OTdDNS42MTkxNCAyLjgxMjUgNS44NTc0MiAzLjAwMTk1IDYuMDUyNzMgMy4yMzYzM0M2LjI1MTk1IDMuNDY2OCA2LjQwNDMgMy43NDAyMyA2LjUwOTc3IDQuMDU2NjRDNi42MTkxNCA0LjM2OTE0IDYuNjczODMgNC43MjA3IDYuNjczODMgNS4xMTEzM0g1LjA0NDkyQzUuMDQ0OTIgNC42Mzg2NyA0LjkzNzUgNC4yODEyNSA0LjcyMjY2IDQuMDM5MDZDNC41MDc4MSAzLjc5Mjk3IDQuMjE2OCAzLjY2OTkyIDMuODQ5NjEgMy42Njk5MkMzLjY1MDM5IDMuNjY5OTIgMy40NzY1NiAzLjY5NzI3IDMuMzI4MTIgMy43NTE5NUMzLjE4MzU5IDMuODAyNzMgMy4wNjQ0NSAzLjg3Njk1IDIuOTcwNyAzLjk3NDYxQzIuODc2OTUgNC4wNjgzNiAyLjgwNjY0IDQuMTc5NjkgMi43NTk3NyA0LjMwODU5QzIuNzE2OCA0LjQzNzUgMi42OTUzMSA0LjU3ODEyIDIuNjk1MzEgNC43MzA0N0MyLjY5NTMxIDQuODgyODEgMi43MTY4IDUuMDE5NTMgMi43NTk3NyA1LjE0MDYyQzIuODA2NjQgNS4yNTc4MSAyLjg4MjgxIDUuMzY3MTkgMi45ODgyOCA1LjQ2ODc1QzMuMDk3NjYgNS41NzAzMSAzLjI0MDIzIDUuNjY3OTcgMy40MTYwMiA1Ljc2MTcyQzMuNTkxOCA1Ljg1MTU2IDMuODEwNTUgNS45NDMzNiA0LjA3MjI3IDYuMDM3MTFDNC40NjY4IDYuMTg1NTUgNC44MjQyMiA2LjMzOTg0IDUuMTQ0NTMgNi41QzUuNDY0ODQgNi42NTYyNSA1LjczODI4IDYuODM5ODQgNS45NjQ4NCA3LjA1MDc4QzYuMTk1MzEgNy4yNTc4MSA2LjM3MTA5IDcuNSA2LjQ5MjE5IDcuNzc3MzRDNi42MTcxOSA4LjA1MDc4IDYuNjc5NjkgOC4zNzUgNi42Nzk2OSA4Ljc1QzYuNjc5NjkgOS4wOTM3NSA2LjYyMzA1IDkuNDA0MyA2LjUwOTc3IDkuNjgxNjRDNi4zOTY0OCA5Ljk1NTA4IDYuMjM0MzggMTAuMTkxNCA2LjAyMzQ0IDEwLjM5MDZDNS44MTI1IDEwLjU4OTggNS41NTg1OSAxMC43NSA1LjI2MTcyIDEwLjg3MTFDNC45NjQ4NCAxMC45ODgzIDQuNjMyODEgMTEuMDY0NSA0LjI2NTYyIDExLjA5OTZWMTIuMjQ4SDMuMzMzOThWMTEuMDk5NkMzLjAwMTk1IDExLjA2ODQgMi42Nzk2OSAxMC45OTYxIDIuMzY3MTkgMTAuODgyOEMyLjA1NDY5IDEwLjc2NTYgMS43NzczNCAxMC41OTc3IDEuNTM1MTYgMTAuMzc4OUMxLjI5Njg4IDEwLjE2MDIgMS4xMDU0NyA5Ljg4NDc3IDAuOTYwOTM4IDkuNTUyNzNDMC44MTY0MDYgOS4yMTY4IDAuNzQ0MTQxIDguODE0NDUgMC43NDQxNDEgOC4zNDU3SDIuMzc4OTFDMi4zNzg5MSA4LjYyNjk1IDIuNDE5OTIgOC44NjMyOCAyLjUwMTk1IDkuMDU0NjlDMi41ODM5OCA5LjI0MjE5IDIuNjg5NDUgOS4zOTI1OCAyLjgxODM2IDkuNTA1ODZDMi45NTExNyA5LjYxNTIzIDMuMTAxNTYgOS42OTMzNiAzLjI2OTUzIDkuNzQwMjNDMy40Mzc1IDkuNzg3MTEgMy42MDkzOCA5LjgxMDU1IDMuNzg1MTYgOS44MTA1NUM0LjIwMzEyIDkuODEwNTUgNC41MTk1MyA5LjcxMjg5IDQuNzM0MzggOS41MTc1OEM0Ljk0OTIyIDkuMzIyMjcgNS4wNTY2NCA5LjA3MDMxIDUuMDU2NjQgOC43NjE3MlpNMTMuNDE4IDEyLjI3MTVIOC4wNzQyMlYxMUgxMy40MThWMTIuMjcxNVoiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMuOTUyNjQgNikiIGZpbGw9IndoaXRlIi8+Cjwvc3ZnPgo=);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtdGV4dC1lZGl0b3ItaWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xNSAxNUgzdjJoMTJ2LTJ6bTAtOEgzdjJoMTJWN3pNMyAxM2gxOHYtMkgzdjJ6bTAgOGgxOHYtMkgzdjJ6TTMgM3YyaDE4VjNIM3oiLz4KPC9zdmc+Cg==);
  --jp-icon-toc: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik03LDVIMjFWN0g3VjVNNywxM1YxMUgyMVYxM0g3TTQsNC41QTEuNSwxLjUgMCAwLDEgNS41LDZBMS41LDEuNSAwIDAsMSA0LDcuNUExLjUsMS41IDAgMCwxIDIuNSw2QTEuNSwxLjUgMCAwLDEgNCw0LjVNNCwxMC41QTEuNSwxLjUgMCAwLDEgNS41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMy41QTEuNSwxLjUgMCAwLDEgMi41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMC41TTcsMTlWMTdIMjFWMTlIN000LDE2LjVBMS41LDEuNSAwIDAsMSA1LjUsMThBMS41LDEuNSAwIDAsMSA0LDE5LjVBMS41LDEuNSAwIDAsMSAyLjUsMThBMS41LDEuNSAwIDAsMSA0LDE2LjVaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tree-view: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMiAxMVYzaC03djNIOVYzSDJ2OGg3VjhoMnYxMGg0djNoN3YtOGgtN3YzaC0yVjhoMnYzeiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-user: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE2IDdhNCA0IDAgMTEtOCAwIDQgNCAwIDAxOCAwek0xMiAxNGE3IDcgMCAwMC03IDdoMTRhNyA3IDAgMDAtNy03eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-users: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZlcnNpb249IjEuMSIgdmlld0JveD0iMCAwIDM2IDI0IiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgogPGcgY2xhc3M9ImpwLWljb24zIiB0cmFuc2Zvcm09Im1hdHJpeCgxLjczMjcgMCAwIDEuNzMyNyAtMy42MjgyIC4wOTk1NzcpIiBmaWxsPSIjNjE2MTYxIj4KICA8cGF0aCB0cmFuc2Zvcm09Im1hdHJpeCgxLjUsMCwwLDEuNSwwLC02KSIgZD0ibTEyLjE4NiA3LjUwOThjLTEuMDUzNSAwLTEuOTc1NyAwLjU2NjUtMi40Nzg1IDEuNDEwMiAwLjc1MDYxIDAuMzEyNzcgMS4zOTc0IDAuODI2NDggMS44NzMgMS40NzI3aDMuNDg2M2MwLTEuNTkyLTEuMjg4OS0yLjg4MjgtMi44ODA5LTIuODgyOHoiLz4KICA8cGF0aCBkPSJtMjAuNDY1IDIuMzg5NWEyLjE4ODUgMi4xODg1IDAgMCAxLTIuMTg4NCAyLjE4ODUgMi4xODg1IDIuMTg4NSAwIDAgMS0yLjE4ODUtMi4xODg1IDIuMTg4NSAyLjE4ODUgMCAwIDEgMi4xODg1LTIuMTg4NSAyLjE4ODUgMi4xODg1IDAgMCAxIDIuMTg4NCAyLjE4ODV6Ii8+CiAgPHBhdGggdHJhbnNmb3JtPSJtYXRyaXgoMS41LDAsMCwxLjUsMCwtNikiIGQ9Im0zLjU4OTggOC40MjE5Yy0xLjExMjYgMC0yLjAxMzcgMC45MDExMS0yLjAxMzcgMi4wMTM3aDIuODE0NWMwLjI2Nzk3LTAuMzczMDkgMC41OTA3LTAuNzA0MzUgMC45NTg5OC0wLjk3ODUyLTAuMzQ0MzMtMC42MTY4OC0xLjAwMzEtMS4wMzUyLTEuNzU5OC0xLjAzNTJ6Ii8+CiAgPHBhdGggZD0ibTYuOTE1NCA0LjYyM2ExLjUyOTQgMS41Mjk0IDAgMCAxLTEuNTI5NCAxLjUyOTQgMS41Mjk0IDEuNTI5NCAwIDAgMS0xLjUyOTQtMS41Mjk0IDEuNTI5NCAxLjUyOTQgMCAwIDEgMS41Mjk0LTEuNTI5NCAxLjUyOTQgMS41Mjk0IDAgMCAxIDEuNTI5NCAxLjUyOTR6Ii8+CiAgPHBhdGggZD0ibTYuMTM1IDEzLjUzNWMwLTMuMjM5MiAyLjYyNTktNS44NjUgNS44NjUtNS44NjUgMy4yMzkyIDAgNS44NjUgMi42MjU5IDUuODY1IDUuODY1eiIvPgogIDxjaXJjbGUgY3g9IjEyIiBjeT0iMy43Njg1IiByPSIyLjk2ODUiLz4KIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-word: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KIDxnIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzQxNDE0MSI+CiAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiA8L2c+CiA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSguNDMgLjA0MDEpIiBmaWxsPSIjZmZmIj4KICA8cGF0aCBkPSJtNC4xNCA4Ljc2cTAuMDY4Mi0xLjg5IDIuNDItMS44OSAxLjE2IDAgMS42OCAwLjQyIDAuNTY3IDAuNDEgMC41NjcgMS4xNnYzLjQ3cTAgMC40NjIgMC41MTQgMC40NjIgMC4xMDMgMCAwLjItMC4wMjMxdjAuNzE0cS0wLjM5OSAwLjEwMy0wLjY1MSAwLjEwMy0wLjQ1MiAwLTAuNjkzLTAuMjItMC4yMzEtMC4yLTAuMjg0LTAuNjYyLTAuOTU2IDAuODcyLTIgMC44NzItMC45MDMgMC0xLjQ3LTAuNDcyLTAuNTI1LTAuNDcyLTAuNTI1LTEuMjYgMC0wLjI2MiAwLjA0NTItMC40NzIgMC4wNTY3LTAuMjIgMC4xMTYtMC4zNzggMC4wNjgyLTAuMTY4IDAuMjMxLTAuMzA0IDAuMTU4LTAuMTQ3IDAuMjYyLTAuMjQyIDAuMTE2LTAuMDkxNCAwLjM2OC0wLjE2OCAwLjI2Mi0wLjA5MTQgMC4zOTktMC4xMjYgMC4xMzYtMC4wNDUyIDAuNDcyLTAuMTAzIDAuMzM2LTAuMDU3OCAwLjUwNC0wLjA3OTggMC4xNTgtMC4wMjMxIDAuNTY3LTAuMDc5OCAwLjU1Ni0wLjA2ODIgMC43NzctMC4yMjEgMC4yMi0wLjE1MiAwLjIyLTAuNDQxdi0wLjI1MnEwLTAuNDMtMC4zNTctMC42NjItMC4zMzYtMC4yMzEtMC45NzYtMC4yMzEtMC42NjIgMC0wLjk5OCAwLjI2Mi0wLjMzNiAwLjI1Mi0wLjM5OSAwLjc5OHptMS44OSAzLjY4cTAuNzg4IDAgMS4yNi0wLjQxIDAuNTA0LTAuNDIgMC41MDQtMC45MDN2LTEuMDVxLTAuMjg0IDAuMTM2LTAuODYxIDAuMjMxLTAuNTY3IDAuMDkxNC0wLjk4NyAwLjE1OC0wLjQyIDAuMDY4Mi0wLjc2NiAwLjMyNi0wLjMzNiAwLjI1Mi0wLjMzNiAwLjcwNHQwLjMwNCAwLjcwNCAwLjg2MSAwLjI1MnoiIHN0cm9rZS13aWR0aD0iMS4wNSIvPgogIDxwYXRoIGQ9Im0xMCA0LjU2aDAuOTQ1djMuMTVxMC42NTEtMC45NzYgMS44OS0wLjk3NiAxLjE2IDAgMS44OSAwLjg0IDAuNjgyIDAuODQgMC42ODIgMi4zMSAwIDEuNDctMC43MDQgMi40Mi0wLjcwNCAwLjg4Mi0xLjg5IDAuODgyLTEuMjYgMC0xLjg5LTEuMDJ2MC43NjZoLTAuODV6bTIuNjIgMy4wNHEtMC43NDYgMC0xLjE2IDAuNjQtMC40NTIgMC42My0wLjQ1MiAxLjY4IDAgMS4wNSAwLjQ1MiAxLjY4dDEuMTYgMC42M3EwLjc3NyAwIDEuMjYtMC42MyAwLjQ5NC0wLjY0IDAuNDk0LTEuNjggMC0xLjA1LTAuNDcyLTEuNjgtMC40NjItMC42NC0xLjI2LTAuNjR6IiBzdHJva2Utd2lkdGg9IjEuMDUiLz4KICA8cGF0aCBkPSJtMi43MyAxNS44IDEzLjYgMC4wMDgxYzAuMDA2OSAwIDAtMi42IDAtMi42IDAtMC4wMDc4LTEuMTUgMC0xLjE1IDAtMC4wMDY5IDAtMC4wMDgzIDEuNS0wLjAwODMgMS41LTJlLTMgLTAuMDAxNC0xMS4zLTAuMDAxNC0xMS4zLTAuMDAxNGwtMC4wMDU5Mi0xLjVjMC0wLjAwNzgtMS4xNyAwLjAwMTMtMS4xNyAwLjAwMTN6IiBzdHJva2Utd2lkdGg9Ii45NzUiLz4KIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddAboveIcon {
  background-image: var(--jp-icon-add-above);
}

.jp-AddBelowIcon {
  background-image: var(--jp-icon-add-below);
}

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}

.jp-BellIcon {
  background-image: var(--jp-icon-bell);
}

.jp-BugDotIcon {
  background-image: var(--jp-icon-bug-dot);
}

.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}

.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}

.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}

.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}

.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}

.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}

.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}

.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}

.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}

.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}

.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}

.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}

.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}

.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}

.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}

.jp-CodeCheckIcon {
  background-image: var(--jp-icon-code-check);
}

.jp-CodeIcon {
  background-image: var(--jp-icon-code);
}

.jp-CollapseAllIcon {
  background-image: var(--jp-icon-collapse-all);
}

.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}

.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}

.jp-CopyrightIcon {
  background-image: var(--jp-icon-copyright);
}

.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}

.jp-DeleteIcon {
  background-image: var(--jp-icon-delete);
}

.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}

.jp-DuplicateIcon {
  background-image: var(--jp-icon-duplicate);
}

.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}

.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}

.jp-ErrorIcon {
  background-image: var(--jp-icon-error);
}

.jp-ExpandAllIcon {
  background-image: var(--jp-icon-expand-all);
}

.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}

.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}

.jp-FileIcon {
  background-image: var(--jp-icon-file);
}

.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}

.jp-FilterDotIcon {
  background-image: var(--jp-icon-filter-dot);
}

.jp-FilterIcon {
  background-image: var(--jp-icon-filter);
}

.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}

.jp-FolderFavoriteIcon {
  background-image: var(--jp-icon-folder-favorite);
}

.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}

.jp-HomeIcon {
  background-image: var(--jp-icon-home);
}

.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}

.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}

.jp-InfoIcon {
  background-image: var(--jp-icon-info);
}

.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}

.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}

.jp-JuliaIcon {
  background-image: var(--jp-icon-julia);
}

.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}

.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}

.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}

.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}

.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}

.jp-LaunchIcon {
  background-image: var(--jp-icon-launch);
}

.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}

.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}

.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}

.jp-ListIcon {
  background-image: var(--jp-icon-list);
}

.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}

.jp-MoveDownIcon {
  background-image: var(--jp-icon-move-down);
}

.jp-MoveUpIcon {
  background-image: var(--jp-icon-move-up);
}

.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}

.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}

.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}

.jp-NumberingIcon {
  background-image: var(--jp-icon-numbering);
}

.jp-OfflineBoltIcon {
  background-image: var(--jp-icon-offline-bolt);
}

.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}

.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}

.jp-PdfIcon {
  background-image: var(--jp-icon-pdf);
}

.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}

.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}

.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}

.jp-RedoIcon {
  background-image: var(--jp-icon-redo);
}

.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}

.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}

.jp-RunIcon {
  background-image: var(--jp-icon-run);
}

.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}

.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}

.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}

.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}

.jp-ShareIcon {
  background-image: var(--jp-icon-share);
}

.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}

.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}

.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}

.jp-TableRowsIcon {
  background-image: var(--jp-icon-table-rows);
}

.jp-TagIcon {
  background-image: var(--jp-icon-tag);
}

.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}

.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}

.jp-TocIcon {
  background-image: var(--jp-icon-toc);
}

.jp-TreeViewIcon {
  background-image: var(--jp-icon-tree-view);
}

.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}

.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}

.jp-UserIcon {
  background-image: var(--jp-icon-user);
}

.jp-UsersIcon {
  background-image: var(--jp-icon-users);
}

.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}

.jp-WordIcon {
  background-image: var(--jp-icon-word);
}

.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.lm-TabBar .lm-TabBar-addButton {
  align-items: center;
  display: flex;
  padding: 4px;
  padding-bottom: 5px;
  margin-right: 1px;
  background-color: var(--jp-layout-color2);
}

.lm-TabBar .lm-TabBar-addButton:hover {
  background-color: var(--jp-layout-color1);
}

.lm-DockPanel-tabBar .lm-TabBar-tab {
  width: var(--jp-private-horizontal-tab-width);
}

.lm-DockPanel-tabBar .lm-TabBar-content {
  flex: unset;
}

.lm-DockPanel-tabBar[data-orientation='horizontal'] {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}

/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}

.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}

.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}

.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}

.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}

.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}

.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}

.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}

.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}

/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}

.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}

.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}

.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}

.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}

.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}

.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}

/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}

.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}

.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}

.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}

.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}

.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}

.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

.jp-icon-dot[fill] {
  fill: var(--jp-warn-color0);
}

.jp-jupyter-icon-color[fill] {
  fill: var(--jp-jupyter-icon-color, var(--jp-warn-color0));
}

.jp-notebook-icon-color[fill] {
  fill: var(--jp-notebook-icon-color, var(--jp-warn-color0));
}

.jp-json-icon-color[fill] {
  fill: var(--jp-json-icon-color, var(--jp-warn-color1));
}

.jp-console-icon-color[fill] {
  fill: var(--jp-console-icon-color, white);
}

.jp-console-icon-background-color[fill] {
  fill: var(--jp-console-icon-background-color, var(--jp-brand-color1));
}

.jp-terminal-icon-color[fill] {
  fill: var(--jp-terminal-icon-color, var(--jp-layout-color2));
}

.jp-terminal-icon-background-color[fill] {
  fill: var(
    --jp-terminal-icon-background-color,
    var(--jp-inverse-layout-color2)
  );
}

.jp-text-editor-icon-color[fill] {
  fill: var(--jp-text-editor-icon-color, var(--jp-inverse-layout-color3));
}

.jp-inspector-icon-color[fill] {
  fill: var(--jp-inspector-icon-color, var(--jp-inverse-layout-color3));
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* stylelint-disable selector-max-class, selector-max-compound-selectors */

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}

.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* stylelint-enable selector-max-class, selector-max-compound-selectors */

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) .jp-icon-hoverShow-content {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `lm-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FormGroup-content fieldset {
  border: none;
  padding: 0;
  min-width: 0;
  width: 100%;
}

/* stylelint-disable selector-max-type */

.jp-FormGroup-content fieldset .jp-inputFieldWrapper input,
.jp-FormGroup-content fieldset .jp-inputFieldWrapper select,
.jp-FormGroup-content fieldset .jp-inputFieldWrapper textarea {
  font-size: var(--jp-content-font-size2);
  border-color: var(--jp-input-border-color);
  border-style: solid;
  border-radius: var(--jp-border-radius);
  border-width: 1px;
  padding: 6px 8px;
  background: none;
  color: var(--jp-ui-font-color0);
  height: inherit;
}

.jp-FormGroup-content fieldset input[type='checkbox'] {
  position: relative;
  top: 2px;
  margin-left: 0;
}

.jp-FormGroup-content button.jp-mod-styled {
  cursor: pointer;
}

.jp-FormGroup-content .checkbox label {
  cursor: pointer;
  font-size: var(--jp-content-font-size1);
}

.jp-FormGroup-content .jp-root > fieldset > legend {
  display: none;
}

.jp-FormGroup-content .jp-root > fieldset > p {
  display: none;
}

/** copy of `input.jp-mod-styled:focus` style */
.jp-FormGroup-content fieldset input:focus,
.jp-FormGroup-content fieldset select:focus {
  -moz-outline-radius: unset;
  outline: var(--jp-border-width) solid var(--md-blue-500);
  outline-offset: -1px;
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-FormGroup-content fieldset input:hover:not(:focus),
.jp-FormGroup-content fieldset select:hover:not(:focus) {
  background-color: var(--jp-border-color2);
}

/* stylelint-enable selector-max-type */

.jp-FormGroup-content .checkbox .field-description {
  /* Disable default description field for checkbox:
   because other widgets do not have description fields,
   we add descriptions to each widget on the field level.
  */
  display: none;
}

.jp-FormGroup-content #root__description {
  display: none;
}

.jp-FormGroup-content .jp-modifiedIndicator {
  width: 5px;
  background-color: var(--jp-brand-color2);
  margin-top: 0;
  margin-left: calc(var(--jp-private-settingeditor-modifier-indent) * -1);
  flex-shrink: 0;
}

.jp-FormGroup-content .jp-modifiedIndicator.jp-errorIndicator {
  background-color: var(--jp-error-color0);
  margin-right: 0.5em;
}

/* RJSF ARRAY style */

.jp-arrayFieldWrapper legend {
  font-size: var(--jp-content-font-size2);
  color: var(--jp-ui-font-color0);
  flex-basis: 100%;
  padding: 4px 0;
  font-weight: var(--jp-content-heading-font-weight);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-arrayFieldWrapper .field-description {
  padding: 4px 0;
  white-space: pre-wrap;
}

.jp-arrayFieldWrapper .array-item {
  width: 100%;
  border: 1px solid var(--jp-border-color2);
  border-radius: 4px;
  margin: 4px;
}

.jp-ArrayOperations {
  display: flex;
  margin-left: 8px;
}

.jp-ArrayOperationsButton {
  margin: 2px;
}

.jp-ArrayOperationsButton .jp-icon3[fill] {
  fill: var(--jp-ui-font-color0);
}

button.jp-ArrayOperationsButton.jp-mod-styled:disabled {
  cursor: not-allowed;
  opacity: 0.5;
}

/* RJSF form validation error */

.jp-FormGroup-content .validationErrors {
  color: var(--jp-error-color0);
}

/* Hide panel level error as duplicated the field level error */
.jp-FormGroup-content .panel.errors {
  display: none;
}

/* RJSF normal content (settings-editor) */

.jp-FormGroup-contentNormal {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.jp-FormGroup-contentNormal .jp-FormGroup-contentItem {
  margin-left: 7px;
  color: var(--jp-ui-font-color0);
}

.jp-FormGroup-contentNormal .jp-FormGroup-description {
  flex-basis: 100%;
  padding: 4px 7px;
}

.jp-FormGroup-contentNormal .jp-FormGroup-default {
  flex-basis: 100%;
  padding: 4px 7px;
}

.jp-FormGroup-contentNormal .jp-FormGroup-fieldLabel {
  font-size: var(--jp-content-font-size1);
  font-weight: normal;
  min-width: 120px;
}

.jp-FormGroup-contentNormal fieldset:not(:first-child) {
  margin-left: 7px;
}

.jp-FormGroup-contentNormal .field-array-of-string .array-item {
  /* Display `jp-ArrayOperations` buttons side-by-side with content except
    for small screens where flex-wrap will place them one below the other.
  */
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.jp-FormGroup-contentNormal .jp-objectFieldWrapper .form-group {
  padding: 2px 8px 2px var(--jp-private-settingeditor-modifier-indent);
  margin-top: 2px;
}

/* RJSF compact content (metadata-form) */

.jp-FormGroup-content.jp-FormGroup-contentCompact {
  width: 100%;
}

.jp-FormGroup-contentCompact .form-group {
  display: flex;
  padding: 0.5em 0.2em 0.5em 0;
}

.jp-FormGroup-contentCompact
  .jp-FormGroup-compactTitle
  .jp-FormGroup-description {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color2);
}

.jp-FormGroup-contentCompact .jp-FormGroup-fieldLabel {
  padding-bottom: 0.3em;
}

.jp-FormGroup-contentCompact .jp-inputFieldWrapper .form-control {
  width: 100%;
  box-sizing: border-box;
}

.jp-FormGroup-contentCompact .jp-arrayFieldWrapper .jp-FormGroup-compactTitle {
  padding-bottom: 7px;
}

.jp-FormGroup-contentCompact
  .jp-objectFieldWrapper
  .jp-objectFieldWrapper
  .form-group {
  padding: 2px 8px 2px var(--jp-private-settingeditor-modifier-indent);
  margin-top: 2px;
}

.jp-FormGroup-contentCompact ul.error-detail {
  margin-block-start: 0.5em;
  margin-block-end: 0.5em;
  padding-inline-start: 1em;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-SidePanel {
  display: flex;
  flex-direction: column;
  min-width: var(--jp-sidebar-min-width);
  overflow-y: auto;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size1);
}

.jp-SidePanel-header {
  flex: 0 0 auto;
  display: flex;
  border-bottom: var(--jp-border-width) solid var(--jp-border-color2);
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin: 0;
  padding: 2px;
  text-transform: uppercase;
}

.jp-SidePanel-toolbar {
  flex: 0 0 auto;
}

.jp-SidePanel-content {
  flex: 1 1 auto;
}

.jp-SidePanel-toolbar,
.jp-AccordionPanel-toolbar {
  height: var(--jp-private-toolbar-height);
}

.jp-SidePanel-toolbar.jp-Toolbar-micro {
  display: none;
}

.lm-AccordionPanel .jp-AccordionPanel-title {
  box-sizing: border-box;
  line-height: 25px;
  margin: 0;
  display: flex;
  align-items: center;
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  font-size: var(--jp-ui-font-size0);
}

.jp-AccordionPanel-title {
  cursor: pointer;
  user-select: none;
  -moz-user-select: none;
  -webkit-user-select: none;
  text-transform: uppercase;
}

.lm-AccordionPanel[data-orientation='horizontal'] > .jp-AccordionPanel-title {
  /* Title is rotated for horizontal accordion panel using CSS */
  display: block;
  transform-origin: top left;
  transform: rotate(-90deg) translate(-100%);
}

.jp-AccordionPanel-title .lm-AccordionPanel-titleLabel {
  user-select: none;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}

.jp-AccordionPanel-title .lm-AccordionPanel-titleCollapser {
  transform: rotate(-90deg);
  margin: auto 0;
  height: 16px;
}

.jp-AccordionPanel-title.lm-mod-expanded .lm-AccordionPanel-titleCollapser {
  transform: rotate(0deg);
}

.lm-AccordionPanel .jp-AccordionPanel-toolbar {
  background: none;
  box-shadow: none;
  border: none;
  margin-left: auto;
}

.lm-AccordionPanel .lm-SplitPanel-handle:hover {
  background: var(--jp-layout-color3);
}

.jp-text-truncated {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent::before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent::after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input[type='checkbox'].jp-mod-styled {
  appearance: checkbox;
  -webkit-appearance: checkbox;
  -moz-appearance: checkbox;
  height: auto;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper:not(.multiple) {
  height: 28px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

select.jp-mod-styled:not([multiple]) {
  height: 32px;
}

select.jp-mod-styled[multiple] {
  max-height: 200px;
  overflow-y: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-switch {
  display: flex;
  align-items: center;
  padding-left: 4px;
  padding-right: 4px;
  font-size: var(--jp-ui-font-size1);
  background-color: transparent;
  color: var(--jp-ui-font-color1);
  border: none;
  height: 20px;
}

.jp-switch:hover {
  background-color: var(--jp-layout-color2);
}

.jp-switch-label {
  margin-right: 5px;
  font-family: var(--jp-ui-font-family);
}

.jp-switch-track {
  cursor: pointer;
  background-color: var(--jp-switch-color, var(--jp-border-color1));
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 34px;
  height: 16px;
  width: 35px;
  position: relative;
}

.jp-switch-track::before {
  content: '';
  position: absolute;
  height: 10px;
  width: 10px;
  margin: 3px;
  left: 0;
  background-color: var(--jp-ui-inverse-font-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 50%;
}

.jp-switch[aria-checked='true'] .jp-switch-track {
  background-color: var(--jp-switch-true-position-color, var(--jp-warn-color0));
}

.jp-switch[aria-checked='true'] .jp-switch-track::before {
  /* track width (35) - margins (3 + 3) - thumb width (10) */
  left: 19px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 8;
  overflow-x: hidden;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0;
  margin: 0;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0 6px;
  margin: 0;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent > span {
  padding: 0;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
  font-family: var(--jp-ui-font-family);
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar.jp-Toolbar-micro {
  padding: 0;
  min-height: 0;
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar {
  border: none;
  box-shadow: none;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-WindowedPanel-outer {
  position: relative;
  overflow-y: auto;
}

.jp-WindowedPanel-inner {
  position: relative;
}

.jp-WindowedPanel-window {
  position: absolute;
  left: 0;
  right: 0;
  overflow: visible;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

body {
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
}

/* Disable native link decoration styles everywhere outside of dialog boxes */
a {
  text-decoration: unset;
  color: unset;
}

a:hover {
  text-decoration: unset;
  color: unset;
}

/* Accessibility for links inside dialog box text */
.jp-Dialog-content a {
  text-decoration: revert;
  color: var(--jp-content-link-color);
}

.jp-Dialog-content a:hover {
  text-decoration: revert;
}

/* Styles for ui-components */
.jp-Button {
  color: var(--jp-ui-font-color2);
  border-radius: var(--jp-border-radius);
  padding: 0 12px;
  font-size: var(--jp-ui-font-size1);

  /* Copy from blueprint 3 */
  display: inline-flex;
  flex-direction: row;
  border: none;
  cursor: pointer;
  align-items: center;
  justify-content: center;
  text-align: left;
  vertical-align: middle;
  min-height: 30px;
  min-width: 30px;
}

.jp-Button:disabled {
  cursor: not-allowed;
}

.jp-Button:empty {
  padding: 0 !important;
}

.jp-Button.jp-mod-small {
  min-height: 24px;
  min-width: 24px;
  font-size: 12px;
  padding: 0 7px;
}

/* Use our own theme for hover styles */
.jp-Button.jp-mod-minimal:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Button.jp-mod-minimal {
  background: none;
}

.jp-InputGroup {
  display: block;
  position: relative;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border: none;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
  padding-bottom: 0;
  padding-top: 0;
  padding-left: 10px;
  padding-right: 28px;
  position: relative;
  width: 100%;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  font-size: 14px;
  font-weight: 400;
  height: 30px;
  line-height: 30px;
  outline: none;
  vertical-align: middle;
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input:disabled {
  cursor: not-allowed;
  resize: block;
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color2);
}

.jp-InputGroup input:disabled ~ span {
  cursor: not-allowed;
  color: var(--jp-ui-font-color2);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color2);
}

.jp-InputGroupAction {
  position: absolute;
  bottom: 1px;
  right: 0;
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

.jp-HTMLSelect.jp-DefaultStyle select:disabled {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color2);
  cursor: not-allowed;
  resize: block;
}

.jp-HTMLSelect.jp-DefaultStyle select:disabled ~ span {
  cursor: not-allowed;
}

/* Use our own theme for hover and option styles */
/* stylelint-disable-next-line selector-max-type */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}

select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-StatusBar-Widget {
  display: flex;
  align-items: center;
  background: var(--jp-layout-color2);
  min-height: var(--jp-statusbar-height);
  justify-content: space-between;
  padding: 0 10px;
}

.jp-StatusBar-Left {
  display: flex;
  align-items: center;
  flex-direction: row;
}

.jp-StatusBar-Middle {
  display: flex;
  align-items: center;
}

.jp-StatusBar-Right {
  display: flex;
  align-items: center;
  flex-direction: row-reverse;
}

.jp-StatusBar-Item {
  max-height: var(--jp-statusbar-height);
  margin: 0 2px;
  height: var(--jp-statusbar-height);
  white-space: nowrap;
  text-overflow: ellipsis;
  color: var(--jp-ui-font-color1);
  padding: 0 6px;
}

.jp-mod-highlighted:hover {
  background-color: var(--jp-layout-color3);
}

.jp-mod-clicked {
  background-color: var(--jp-brand-color1);
}

.jp-mod-clicked:hover {
  background-color: var(--jp-brand-color0);
}

.jp-mod-clicked .jp-StatusBar-TextItem {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-StatusBar-HoverItem {
  box-shadow: '0px 4px 4px rgba(0, 0, 0, 0.25)';
}

.jp-StatusBar-TextItem {
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  line-height: 24px;
  color: var(--jp-ui-font-color1);
}

.jp-StatusBar-GroupItem {
  display: flex;
  align-items: center;
  flex-direction: row;
}

.jp-Statusbar-ProgressCircle svg {
  display: block;
  margin: 0 auto;
  width: 16px;
  height: 24px;
  align-self: normal;
}

.jp-Statusbar-ProgressCircle path {
  fill: var(--jp-inverse-layout-color3);
}

.jp-Statusbar-ProgressBar-progress-bar {
  height: 10px;
  width: 100px;
  border: solid 0.25px var(--jp-brand-color2);
  border-radius: 3px;
  overflow: hidden;
  align-self: center;
}

.jp-Statusbar-ProgressBar-progress-bar > div {
  background-color: var(--jp-brand-color2);
  background-image: linear-gradient(
    -45deg,
    rgba(255, 255, 255, 0.2) 25%,
    transparent 25%,
    transparent 50%,
    rgba(255, 255, 255, 0.2) 50%,
    rgba(255, 255, 255, 0.2) 75%,
    transparent 75%,
    transparent
  );
  background-size: 40px 40px;
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 14px;
  color: #fff;
  text-align: center;
  animation: jp-Statusbar-ExecutionTime-progress-bar 2s linear infinite;
}

.jp-Statusbar-ProgressBar-progress-bar p {
  color: var(--jp-ui-font-color1);
  font-family: var(--jp-ui-font-family);
  font-size: var(--jp-ui-font-size1);
  line-height: 10px;
  width: 100px;
}

@keyframes jp-Statusbar-ExecutionTime-progress-bar {
  0% {
    background-position: 0 0;
  }

  100% {
    background-position: 40px 40px;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);

  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Modal variant
|----------------------------------------------------------------------------*/

.jp-ModalCommandPalette {
  position: absolute;
  z-index: 10000;
  top: 38px;
  left: 30%;
  margin: 0;
  padding: 4px;
  width: 40%;
  box-shadow: var(--jp-elevation-z4);
  border-radius: 4px;
  background: var(--jp-layout-color0);
}

.jp-ModalCommandPalette .lm-CommandPalette {
  max-height: 40vh;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-close-icon::after {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-header {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-item {
  margin-left: 4px;
  margin-right: 4px;
}

.jp-ModalCommandPalette
  .lm-CommandPalette
  .lm-CommandPalette-item.lm-mod-disabled {
  display: none;
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-SearchIconGroup {
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  padding: 5px 5px 1px;
}

.jp-SearchIconGroup svg {
  height: 20px;
  width: 20px;
}

.jp-SearchIconGroup .jp-icon3[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color2);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item.lm-mod-active {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active .jp-icon-selectable[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.6;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty::after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0;
  left: 0;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px 24px 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);

  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
  resize: both;
}

.jp-Dialog-content.jp-Dialog-content-small {
  max-width: 500px;
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-accept:focus,
button.jp-Dialog-button.jp-mod-styled.jp-mod-warn:focus,
button.jp-Dialog-button.jp-mod-styled.jp-mod-reject:focus {
  outline-offset: 4px;
  -moz-outline-radius: 0;
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-accept:focus {
  outline: 1px solid var(--jp-accept-color-normal, var(--jp-brand-color1));
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-warn:focus {
  outline: 1px solid var(--jp-warn-color-normal, var(--jp-error-color1));
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-reject:focus {
  outline: 1px solid var(--jp-reject-color-normal, var(--md-grey-600));
}

button.jp-Dialog-close-button {
  padding: 0;
  height: 100%;
  min-width: unset;
  min-height: unset;
}

.jp-Dialog-header {
  display: flex;
  justify-content: space-between;
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color1);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-checkbox {
  padding-right: 5px;
}

.jp-Dialog-checkbox > input:focus-visible {
  outline: 1px solid var(--jp-input-active-border-color);
  outline-offset: 1px;
}

.jp-Dialog-spacer {
  flex: 1 1 auto;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-Input-Boolean-Dialog {
  flex-direction: row-reverse;
  align-items: end;
  width: 100%;
}

.jp-Input-Boolean-Dialog > label {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

.jp-MainAreaWidget .jp-MainAreaWidget-error {
  padding: 6px;
}

.jp-MainAreaWidget .jp-MainAreaWidget-error > pre {
  width: auto;
  padding: 10px;
  background: var(--jp-error-color3);
  border: var(--jp-border-width) solid var(--jp-error-color1);
  border-radius: var(--jp-border-radius);
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  white-space: pre-wrap;
  word-wrap: break-word;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;
  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;
  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #a0f;
  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;
  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;
  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;
  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;
  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;
  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;
  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;
  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;
  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;
  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ff0;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;
  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;
  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;
  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;
  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;
  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;
  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

:root {
  /* This is the padding value to fill the gaps between lines containing spans with background color. */
  --jp-private-code-span-padding: calc(
    (var(--jp-code-line-height) - 1) * var(--jp-code-font-size) / 2
  );
}

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0;
  padding: 0;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}

.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}

.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}

.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}

.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}

.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}

.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}

.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}

.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}

.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}

.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}

.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}

.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}

.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}

.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}

.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}

.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);

  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

/* stylelint-disable selector-max-type, selector-max-compound-selectors */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0;
}

/* stylelint-enable selector-max-type, selector-max-compound-selectors */

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  table-layout: fixed;
  margin-left: auto;
  margin-bottom: 1em;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}

[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}

.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}

.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}

.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}

.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}

.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}

.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}

.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}

.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: var(--jp-ui-font-size0);
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-cursor-backdrop {
  position: fixed;
  width: 200px;
  height: 200px;
  margin-top: -100px;
  margin-left: -100px;
  will-change: transform;
  z-index: 100;
}

.lm-mod-drag-image {
  will-change: transform;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-lineFormSearch {
  padding: 4px 12px;
  background-color: var(--jp-layout-color2);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
  font-size: var(--jp-ui-font-size1);
}

.jp-lineFormCaption {
  font-size: var(--jp-ui-font-size0);
  line-height: var(--jp-ui-font-size1);
  margin-top: 4px;
  color: var(--jp-ui-font-color0);
}

.jp-baseLineForm {
  border: none;
  border-radius: 0;
  position: absolute;
  background-size: 16px;
  background-repeat: no-repeat;
  background-position: center;
  outline: none;
}

.jp-lineFormButtonContainer {
  top: 4px;
  right: 8px;
  height: 24px;
  padding: 0 12px;
  width: 12px;
}

.jp-lineFormButtonIcon {
  top: 0;
  right: 0;
  background-color: var(--jp-brand-color1);
  height: 100%;
  width: 100%;
  box-sizing: border-box;
  padding: 4px 6px;
}

.jp-lineFormButton {
  top: 0;
  right: 0;
  background-color: transparent;
  height: 100%;
  width: 100%;
  box-sizing: border-box;
}

.jp-lineFormWrapper {
  overflow: hidden;
  padding: 0 8px;
  border: 1px solid var(--jp-border-color0);
  background-color: var(--jp-input-active-background);
  height: 22px;
}

.jp-lineFormWrapperFocusWithin {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-lineFormInput {
  background: transparent;
  width: 200px;
  height: 100%;
  border: none;
  outline: none;
  color: var(--jp-ui-font-color0);
  line-height: 28px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/
.jp-DocumentSearch-input {
  border: none;
  outline: none;
  color: var(--jp-ui-font-color0);
  font-size: var(--jp-ui-font-size1);
  background-color: var(--jp-layout-color0);
  font-family: var(--jp-ui-font-family);
  padding: 2px 1px;
  resize: none;
}

.jp-DocumentSearch-overlay {
  position: absolute;
  background-color: var(--jp-toolbar-background);
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  border-left: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  top: 0;
  right: 0;
  z-index: 7;
  min-width: 405px;
  padding: 2px;
  font-size: var(--jp-ui-font-size1);

  --jp-private-document-search-button-height: 20px;
}

.jp-DocumentSearch-overlay button {
  background-color: var(--jp-toolbar-background);
  outline: 0;
}

.jp-DocumentSearch-overlay button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-overlay button:active {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-overlay-row {
  display: flex;
  align-items: center;
  margin-bottom: 2px;
}

.jp-DocumentSearch-button-content {
  display: inline-block;
  cursor: pointer;
  box-sizing: border-box;
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-button-content svg {
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-input-wrapper {
  border: var(--jp-border-width) solid var(--jp-border-color0);
  display: flex;
  background-color: var(--jp-layout-color0);
  margin: 2px;
}

.jp-DocumentSearch-input-wrapper:focus-within {
  border-color: var(--jp-cell-editor-active-border-color);
}

.jp-DocumentSearch-toggle-wrapper,
.jp-DocumentSearch-button-wrapper {
  all: initial;
  overflow: hidden;
  display: inline-block;
  border: none;
  box-sizing: border-box;
}

.jp-DocumentSearch-toggle-wrapper {
  width: 14px;
  height: 14px;
}

.jp-DocumentSearch-button-wrapper {
  width: var(--jp-private-document-search-button-height);
  height: var(--jp-private-document-search-button-height);
}

.jp-DocumentSearch-toggle-wrapper:focus,
.jp-DocumentSearch-button-wrapper:focus {
  outline: var(--jp-border-width) solid
    var(--jp-cell-editor-active-border-color);
  outline-offset: -1px;
}

.jp-DocumentSearch-toggle-wrapper,
.jp-DocumentSearch-button-wrapper,
.jp-DocumentSearch-button-content:focus {
  outline: none;
}

.jp-DocumentSearch-toggle-placeholder {
  width: 5px;
}

.jp-DocumentSearch-input-button::before {
  display: block;
  padding-top: 100%;
}

.jp-DocumentSearch-input-button-off {
  opacity: var(--jp-search-toggle-off-opacity);
}

.jp-DocumentSearch-input-button-off:hover {
  opacity: var(--jp-search-toggle-hover-opacity);
}

.jp-DocumentSearch-input-button-on {
  opacity: var(--jp-search-toggle-on-opacity);
}

.jp-DocumentSearch-index-counter {
  padding-left: 10px;
  padding-right: 10px;
  user-select: none;
  min-width: 35px;
  display: inline-block;
}

.jp-DocumentSearch-up-down-wrapper {
  display: inline-block;
  padding-right: 2px;
  margin-left: auto;
  white-space: nowrap;
}

.jp-DocumentSearch-spacer {
  margin-left: auto;
}

.jp-DocumentSearch-up-down-wrapper button {
  outline: 0;
  border: none;
  width: var(--jp-private-document-search-button-height);
  height: var(--jp-private-document-search-button-height);
  vertical-align: middle;
  margin: 1px 5px 2px;
}

.jp-DocumentSearch-up-down-button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-up-down-button:active {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-filter-button {
  border-radius: var(--jp-border-radius);
}

.jp-DocumentSearch-filter-button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-filter-button-enabled {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-filter-button-enabled:hover {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-search-options {
  padding: 0 8px;
  margin-left: 3px;
  width: 100%;
  display: grid;
  justify-content: start;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  justify-items: stretch;
}

.jp-DocumentSearch-search-filter-disabled {
  color: var(--jp-ui-font-color2);
}

.jp-DocumentSearch-search-filter {
  display: flex;
  align-items: center;
  user-select: none;
}

.jp-DocumentSearch-regex-error {
  color: var(--jp-error-color0);
}

.jp-DocumentSearch-replace-button-wrapper {
  overflow: hidden;
  display: inline-block;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color0);
  margin: auto 2px;
  padding: 1px 4px;
  height: calc(var(--jp-private-document-search-button-height) + 2px);
}

.jp-DocumentSearch-replace-button-wrapper:focus {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
}

.jp-DocumentSearch-replace-button {
  display: inline-block;
  text-align: center;
  cursor: pointer;
  box-sizing: border-box;
  color: var(--jp-ui-font-color1);

  /* height - 2 * (padding of wrapper) */
  line-height: calc(var(--jp-private-document-search-button-height) - 2px);
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-replace-button:focus {
  outline: none;
}

.jp-DocumentSearch-replace-wrapper-class {
  margin-left: 14px;
  display: flex;
}

.jp-DocumentSearch-replace-toggle {
  border: none;
  background-color: var(--jp-toolbar-background);
  border-radius: var(--jp-border-radius);
}

.jp-DocumentSearch-replace-toggle:hover {
  background-color: var(--jp-layout-color2);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.cm-editor {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;

  /* Changed to auto to autogrow */
}

.cm-editor pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .cm-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

.jp-CodeMirrorEditor {
  cursor: text;
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .cm-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .cm-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.cm-editor.jp-mod-readOnly .cm-cursor {
  display: none;
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.cm-searching,
.cm-searching span {
  /* `.cm-searching span`: we need to override syntax highlighting */
  background-color: var(--jp-search-unselected-match-background-color);
  color: var(--jp-search-unselected-match-color);
}

.cm-searching::selection,
.cm-searching span::selection {
  background-color: var(--jp-search-unselected-match-background-color);
  color: var(--jp-search-unselected-match-color);
}

.jp-current-match > .cm-searching,
.jp-current-match > .cm-searching span,
.cm-searching > .jp-current-match,
.cm-searching > .jp-current-match span {
  background-color: var(--jp-search-selected-match-background-color);
  color: var(--jp-search-selected-match-color);
}

.jp-current-match > .cm-searching::selection,
.cm-searching > .jp-current-match::selection,
.jp-current-match > .cm-searching span::selection {
  background-color: var(--jp-search-selected-match-background-color);
  color: var(--jp-search-selected-match-color);
}

.cm-trailingspace {
  background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAFCAYAAAB4ka1VAAAAsElEQVQIHQGlAFr/AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA7+r3zKmT0/+pk9P/7+r3zAAAAAAAAAAABAAAAAAAAAAA6OPzM+/q9wAAAAAA6OPzMwAAAAAAAAAAAgAAAAAAAAAAGR8NiRQaCgAZIA0AGR8NiQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQyoYJ/SY80UAAAAASUVORK5CYII=);
  background-position: center left;
  background-repeat: repeat-x;
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/* Styles for shared cursors (remote cursor locations and selected ranges) */
.jp-CodeMirrorEditor .cm-ySelectionCaret {
  position: relative;
  border-left: 1px solid black;
  margin-left: -1px;
  margin-right: -1px;
  box-sizing: border-box;
}

.jp-CodeMirrorEditor .cm-ySelectionCaret > .cm-ySelectionInfo {
  white-space: nowrap;
  position: absolute;
  top: -1.15em;
  padding-bottom: 0.05em;
  left: -1px;
  font-size: 0.95em;
  font-family: var(--jp-ui-font-family);
  font-weight: bold;
  line-height: normal;
  user-select: none;
  color: white;
  padding-left: 2px;
  padding-right: 2px;
  z-index: 101;
  transition: opacity 0.3s ease-in-out;
}

.jp-CodeMirrorEditor .cm-ySelectionInfo {
  transition-delay: 0.7s;
  opacity: 0;
}

.jp-CodeMirrorEditor .cm-ySelectionCaret:hover > .cm-ySelectionInfo {
  opacity: 1;
  transition-delay: 0s;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser .jp-SidePanel-content {
  display: flex;
  flex-direction: column;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  flex-wrap: wrap;
  row-gap: 12px;
  border-bottom: none;
  height: auto;
  margin: 8px 12px 0;
  box-shadow: none;
  padding: 0;
  justify-content: flex-start;
}

.jp-FileBrowser-Panel {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 8px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0 2px;
  padding: 0 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  padding-left: 0;
  padding-right: 2px;
  align-items: center;
  height: unset;
}

.jp-FileBrowser-toolbar > .jp-Toolbar-item .jp-ToolbarButtonComponent {
  width: 40px;
}

/*-----------------------------------------------------------------------------
| Other styles
|----------------------------------------------------------------------------*/

.jp-FileDialog.jp-mod-conflict input {
  color: var(--jp-error-color1);
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

.jp-LastModified-hidden {
  display: none;
}

.jp-FileSize-hidden {
  display: none;
}

.jp-FileBrowser .lm-AccordionPanel > h3:first-child {
  display: none;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  align-items: center;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-DirListing-headerItem.jp-id-filesize {
  flex: 0 0 75px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-id-narrow {
  display: none;
  flex: 0 0 5px;
  padding: 4px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
  color: var(--jp-border-color2);
}

.jp-DirListing-narrow .jp-id-narrow {
  display: block;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-DirListing-content mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.jp-DirListing-content .jp-DirListing-item.jp-mod-selected mark {
  color: var(--jp-ui-inverse-font-color0);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-checkboxWrapper {
  /* Increases hit area of checkbox. */
  padding: 4px;
}

.jp-DirListing-header
  .jp-DirListing-checkboxWrapper
  + .jp-DirListing-headerItem {
  padding-left: 4px;
}

.jp-DirListing-content .jp-DirListing-checkboxWrapper {
  position: relative;
  left: -4px;
  margin: -4px 0 -4px -8px;
}

.jp-DirListing-checkboxWrapper.jp-mod-visible {
  visibility: visible;
}

/* For devices that support hovering, hide checkboxes until hovered, selected...
*/
@media (hover: hover) {
  .jp-DirListing-checkboxWrapper {
    visibility: hidden;
  }

  .jp-DirListing-item:hover .jp-DirListing-checkboxWrapper,
  .jp-DirListing-item.jp-mod-selected .jp-DirListing-checkboxWrapper {
    visibility: visible;
  }
}

.jp-DirListing-item[data-is-dot] {
  opacity: 75%;
}

.jp-DirListing-item.jp-mod-selected {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemText:focus {
  outline-width: 2px;
  outline-color: var(--jp-inverse-layout-color1);
  outline-style: solid;
  outline-offset: 1px;
}

.jp-DirListing-item.jp-mod-selected .jp-DirListing-itemText:focus {
  outline-color: var(--jp-layout-color1);
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-itemFileSize {
  flex: 0 0 90px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon::before {
  color: var(--jp-success-color1);
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.jp-mod-running.jp-mod-selected
  .jp-DirListing-itemIcon::before {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: table;
  table-layout: fixed;
  width: 100%;
  overflow: hidden;
}

.jp-OutputPrompt {
  width: var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);

  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;

  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-OutputArea-prompt {
  display: table-cell;
  vertical-align: top;
}

.jp-OutputArea-output {
  display: table-cell;
  width: 100%;
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea .jp-RenderedText {
  padding-left: 1ch;
}

/**
 * Prompt overlay.
 */

.jp-OutputArea-promptOverlay {
  position: absolute;
  top: 0;
  width: var(--jp-cell-prompt-width);
  height: 100%;
  opacity: 0.5;
}

.jp-OutputArea-promptOverlay:hover {
  background: var(--jp-layout-color2);
  box-shadow: inset 0 0 1px var(--jp-inverse-layout-color0);
  cursor: zoom-out;
}

.jp-mod-outputsScrolled .jp-OutputArea-promptOverlay:hover {
  cursor: zoom-in;
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `lm-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0;
  padding: 0;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

.jp-TrimmedOutputs pre {
  background: var(--jp-layout-color3);
  font-size: calc(var(--jp-code-font-size) * 1.4);
  text-align: center;
  text-transform: uppercase;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/* Hide empty lines in the output area, for instance due to cleared widgets */
.jp-OutputArea-prompt:empty {
  padding: 0;
  border: 0;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0;
  width: 100%;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
  border-top: var(--jp-border-width) solid transparent;
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;

  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;

  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0 0.25em;
  margin: 0 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input::placeholder {
  opacity: 0;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

.jp-Stdin-input:focus::placeholder {
  opacity: 1;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

@media print {
  .jp-OutputArea-child {
    break-inside: avoid-page;
  }
}

/*-----------------------------------------------------------------------------
| Mobile
|----------------------------------------------------------------------------*/
@media only screen and (max-width: 760px) {
  .jp-OutputPrompt {
    display: table-row;
    text-align: left;
  }

  .jp-OutputArea-child .jp-OutputArea-output {
    display: table-row;
    margin-left: var(--jp-notebook-padding);
  }
}

/* Trimmed outputs warning */
.jp-TrimmedOutputs > a {
  margin: 10px;
  text-decoration: none;
  cursor: pointer;
}

.jp-TrimmedOutputs > a:hover {
  text-decoration: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Table of Contents
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toc-active-width: 4px;
}

.jp-TableOfContents {
  display: flex;
  flex-direction: column;
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  height: 100%;
}

.jp-TableOfContents-placeholder {
  text-align: center;
}

.jp-TableOfContents-placeholderContent {
  color: var(--jp-content-font-color2);
  padding: 8px;
}

.jp-TableOfContents-placeholderContent > h3 {
  margin-bottom: var(--jp-content-heading-margin-bottom);
}

.jp-TableOfContents .jp-SidePanel-content {
  overflow-y: auto;
}

.jp-TableOfContents-tree {
  margin: 4px;
}

.jp-TableOfContents ol {
  list-style-type: none;
}

/* stylelint-disable-next-line selector-max-type */
.jp-TableOfContents li > ol {
  /* Align left border with triangle icon center */
  padding-left: 11px;
}

.jp-TableOfContents-content {
  /* left margin for the active heading indicator */
  margin: 0 0 0 var(--jp-private-toc-active-width);
  padding: 0;
  background-color: var(--jp-layout-color1);
}

.jp-tocItem {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-tocItem-heading {
  display: flex;
  cursor: pointer;
}

.jp-tocItem-heading:hover {
  background-color: var(--jp-layout-color2);
}

.jp-tocItem-content {
  display: block;
  padding: 4px 0;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow-x: hidden;
}

.jp-tocItem-collapser {
  height: 20px;
  margin: 2px 2px 0;
  padding: 0;
  background: none;
  border: none;
  cursor: pointer;
}

.jp-tocItem-collapser:hover {
  background-color: var(--jp-layout-color3);
}

/* Active heading indicator */

.jp-tocItem-heading::before {
  content: ' ';
  background: transparent;
  width: var(--jp-private-toc-active-width);
  height: 24px;
  position: absolute;
  left: 0;
  border-radius: var(--jp-border-radius);
}

.jp-tocItem-heading.jp-tocItem-active::before {
  background-color: var(--jp-brand-color1);
}

.jp-tocItem-heading:hover.jp-tocItem-active::before {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0;
  margin: 0;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;

  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0;
  bottom: 0;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

/*
Hiding collapsers in print mode.

Note: input and output wrappers have "display: block" propery in print mode.
*/

@media print {
  .jp-Collapser {
    display: none;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0;
  width: 100%;
  padding: 0;
  margin: 0;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: table;
  table-layout: fixed;
  width: 100%;
  overflow: hidden;
}

.jp-InputArea-editor {
  display: table-cell;
  overflow: hidden;
  vertical-align: top;

  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0;
  background: var(--jp-cell-editor-background);
}

.jp-InputPrompt {
  display: table-cell;
  vertical-align: top;
  width: var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;

  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;

  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/*-----------------------------------------------------------------------------
| Mobile
|----------------------------------------------------------------------------*/
@media only screen and (max-width: 760px) {
  .jp-InputArea-editor {
    display: table-row;
    margin-left: var(--jp-notebook-padding);
  }

  .jp-InputPrompt {
    display: table-row;
    text-align: left;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: table;
  table-layout: fixed;
  width: 100%;
}

.jp-Placeholder-prompt {
  display: table-cell;
  box-sizing: border-box;
}

.jp-Placeholder-content {
  display: table-cell;
  padding: 4px 6px;
  border: 1px solid transparent;
  border-radius: 0;
  background: none;
  box-sizing: border-box;
  cursor: pointer;
}

.jp-Placeholder-contentContainer {
  display: flex;
}

.jp-Placeholder-content:hover,
.jp-InputPlaceholder > .jp-Placeholder-content:hover {
  border-color: var(--jp-layout-color3);
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0 0 2px 0 rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

.jp-PlaceholderText {
  white-space: nowrap;
  overflow-x: hidden;
  color: var(--jp-inverse-layout-color3);
  font-family: var(--jp-code-font-family);
}

.jp-InputPlaceholder > .jp-Placeholder-content {
  border-color: var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0;
  margin: 0;

  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 24em;
  margin-left: var(--jp-private-cell-scrolling-output-offset);
  resize: vertical;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea[style*='height'] {
  max-height: unset;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea::after {
  content: ' ';
  box-shadow: inset 0 0 6px 2px rgb(0 0 0 / 30%);
  width: 100%;
  height: 100%;
  position: sticky;
  bottom: 0;
  top: 0;
  margin-top: -50%;
  float: left;
  display: block;
  pointer-events: none;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-child {
  padding-top: 6px;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  width: calc(
    var(--jp-cell-prompt-width) - var(--jp-private-cell-scrolling-output-offset)
  );
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-promptOverlay {
  left: calc(-1 * var(--jp-private-cell-scrolling-output-offset));
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  display: table-cell;
  width: 100%;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

/* collapseHeadingButton (show always if hiddenCellsButton is _not_ shown) */
.jp-collapseHeadingButton {
  display: flex;
  min-height: var(--jp-cell-collapser-min-height);
  font-size: var(--jp-code-font-size);
  position: absolute;
  background-color: transparent;
  background-size: 25px;
  background-repeat: no-repeat;
  background-position-x: center;
  background-position-y: top;
  background-image: var(--jp-icon-caret-down);
  right: 0;
  top: 0;
  bottom: 0;
}

.jp-collapseHeadingButton.jp-mod-collapsed {
  background-image: var(--jp-icon-caret-right);
}

/*
 set the container font size to match that of content
 so that the nested collapse buttons have the right size
*/
.jp-MarkdownCell .jp-InputPrompt {
  font-size: var(--jp-content-font-size1);
}

/*
  Align collapseHeadingButton with cell top header
  The font sizes are identical to the ones in packages/rendermime/style/base.css
*/
.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='1'] {
  font-size: var(--jp-content-font-size5);
  background-position-y: calc(0.3 * var(--jp-content-font-size5));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='2'] {
  font-size: var(--jp-content-font-size4);
  background-position-y: calc(0.3 * var(--jp-content-font-size4));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='3'] {
  font-size: var(--jp-content-font-size3);
  background-position-y: calc(0.3 * var(--jp-content-font-size3));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='4'] {
  font-size: var(--jp-content-font-size2);
  background-position-y: calc(0.3 * var(--jp-content-font-size2));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='5'] {
  font-size: var(--jp-content-font-size1);
  background-position-y: top;
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='6'] {
  font-size: var(--jp-content-font-size0);
  background-position-y: top;
}

/* collapseHeadingButton (show only on (hover,active) if hiddenCellsButton is shown) */
.jp-Notebook.jp-mod-showHiddenCellsButton .jp-collapseHeadingButton {
  display: none;
}

.jp-Notebook.jp-mod-showHiddenCellsButton
  :is(.jp-MarkdownCell:hover, .jp-mod-active)
  .jp-collapseHeadingButton {
  display: flex;
}

/* showHiddenCellsButton (only show if jp-mod-showHiddenCellsButton is set, which
is a consequence of the showHiddenCellsButton option in Notebook Settings)*/
.jp-Notebook.jp-mod-showHiddenCellsButton .jp-showHiddenCellsButton {
  margin-left: calc(var(--jp-cell-prompt-width) + 2 * var(--jp-code-padding));
  margin-top: var(--jp-code-padding);
  border: 1px solid var(--jp-border-color2);
  background-color: var(--jp-border-color3) !important;
  color: var(--jp-content-font-color0) !important;
  display: flex;
}

.jp-Notebook.jp-mod-showHiddenCellsButton .jp-showHiddenCellsButton:hover {
  background-color: var(--jp-border-color2) !important;
}

.jp-showHiddenCellsButton {
  display: none;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

/*
Using block instead of flex to allow the use of the break-inside CSS property for
cell outputs.
*/

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-notebook-toolbar-padding: 2px 5px 2px 2px;
}

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: var(--jp-notebook-toolbar-padding);

  /* disable paint containment from lumino 2.0 default strict CSS containment */
  contain: style size !important;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

.jp-Toolbar-responsive-popup {
  position: absolute;
  height: fit-content;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: flex-end;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: var(--jp-notebook-toolbar-padding);
  z-index: 1;
  right: 0;
  top: 0;
}

.jp-Toolbar > .jp-Toolbar-responsive-opener {
  margin-left: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-Notebook-ExecutionIndicator {
  position: relative;
  display: inline-block;
  height: 100%;
  z-index: 9997;
}

.jp-Notebook-ExecutionIndicator-tooltip {
  visibility: hidden;
  height: auto;
  width: max-content;
  width: -moz-max-content;
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color1);
  text-align: justify;
  border-radius: 6px;
  padding: 0 5px;
  position: fixed;
  display: table;
}

.jp-Notebook-ExecutionIndicator-tooltip.up {
  transform: translateX(-50%) translateY(-100%) translateY(-32px);
}

.jp-Notebook-ExecutionIndicator-tooltip.down {
  transform: translateX(calc(-100% + 16px)) translateY(5px);
}

.jp-Notebook-ExecutionIndicator-tooltip.hidden {
  display: none;
}

.jp-Notebook-ExecutionIndicator:hover .jp-Notebook-ExecutionIndicator-tooltip {
  visibility: visible;
}

.jp-Notebook-ExecutionIndicator span {
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  color: var(--jp-ui-font-color1);
  line-height: 24px;
  display: block;
}

.jp-Notebook-ExecutionIndicator-progress-bar {
  display: flex;
  justify-content: center;
  height: 100%;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*
 * Execution indicator
 */
.jp-tocItem-content::after {
  content: '';

  /* Must be identical to form a circle */
  width: 12px;
  height: 12px;
  background: none;
  border: none;
  position: absolute;
  right: 0;
}

.jp-tocItem-content[data-running='0']::after {
  border-radius: 50%;
  border: var(--jp-border-width) solid var(--jp-inverse-layout-color3);
  background: none;
}

.jp-tocItem-content[data-running='1']::after {
  border-radius: 50%;
  border: var(--jp-border-width) solid var(--jp-inverse-layout-color3);
  background-color: var(--jp-inverse-layout-color3);
}

.jp-tocItem-content[data-running='0'],
.jp-tocItem-content[data-running='1'] {
  margin-right: 12px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-Notebook-footer {
  height: 27px;
  margin-left: calc(
    var(--jp-cell-prompt-width) + var(--jp-cell-collapser-width) +
      var(--jp-cell-padding)
  );
  width: calc(
    100% -
      (
        var(--jp-cell-prompt-width) + var(--jp-cell-collapser-width) +
          var(--jp-cell-padding) + var(--jp-cell-padding)
      )
  );
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  color: var(--jp-ui-font-color3);
  margin-top: 6px;
  background: none;
  cursor: pointer;
}

.jp-Notebook-footer:focus {
  border-color: var(--jp-cell-editor-active-border-color);
}

/* For devices that support hovering, hide footer until hover */
@media (hover: hover) {
  .jp-Notebook-footer {
    opacity: 0;
  }

  .jp-Notebook-footer:focus,
  .jp-Notebook-footer:hover {
    opacity: 1;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-side-by-side-output-size: 1fr;
  --jp-side-by-side-resized-cell: var(--jp-side-by-side-output-size);
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

/* stylelint-disable selector-max-class */

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-MainAreaWidget-ContainStrict .jp-Notebook * {
  contain: strict;
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* cell is dirty */
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt {
  color: var(--jp-warn-color1);
}

.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt::before {
  color: var(--jp-warn-color1);
  content: '•';
}

.jp-Notebook .jp-Cell.jp-mod-active.jp-mod-dirty .jp-Collapser {
  background: var(--jp-warn-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: block;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0 rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0 rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);

  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-ActiveCellTool {
  padding: 12px 0;
  display: flex;
}

.jp-ActiveCellTool-Content {
  flex: 1 1 auto;
}

.jp-ActiveCellTool .jp-ActiveCellTool-CellContent {
  background: var(--jp-cell-editor-background);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0;
  min-height: 29px;
}

.jp-ActiveCellTool .jp-InputPrompt {
  min-width: calc(var(--jp-cell-prompt-width) * 0.75);
}

.jp-ActiveCellTool-CellContent > pre {
  padding: 5px 4px;
  margin: 0;
  white-space: normal;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label,
.jp-NumberSetter label {
  line-height: 1.4;
}

.jp-NotebookTools .jp-select-wrapper {
  margin-top: 4px;
  margin-bottom: 0;
}

.jp-NumberSetter input {
  width: 100%;
  margin-top: 4px;
}

.jp-NotebookTools .jp-Collapse {
  margin-top: 16px;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Side-by-side Mode (.jp-mod-sideBySide)
|----------------------------------------------------------------------------*/
.jp-mod-sideBySide.jp-Notebook .jp-Notebook-cell {
  margin-top: 3em;
  margin-bottom: 3em;
  margin-left: 5%;
  margin-right: 5%;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell {
  display: grid;
  grid-template-columns: minmax(0, 1fr) min-content minmax(
      0,
      var(--jp-side-by-side-output-size)
    );
  grid-template-rows: auto minmax(0, 1fr) auto;
  grid-template-areas:
    'header header header'
    'input handle output'
    'footer footer footer';
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell.jp-mod-resizedCell {
  grid-template-columns: minmax(0, 1fr) min-content minmax(
      0,
      var(--jp-side-by-side-resized-cell)
    );
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellHeader {
  grid-area: header;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-Cell-inputWrapper {
  grid-area: input;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-Cell-outputWrapper {
  /* overwrite the default margin (no vertical separation needed in side by side move */
  margin-top: 0;
  grid-area: output;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellFooter {
  grid-area: footer;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellResizeHandle {
  grid-area: handle;
  user-select: none;
  display: block;
  height: 100%;
  cursor: ew-resize;
  padding: 0 var(--jp-cell-padding);
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellResizeHandle::after {
  content: '';
  display: block;
  background: var(--jp-border-color2);
  height: 100%;
  width: 5px;
}

.jp-mod-sideBySide.jp-Notebook
  .jp-CodeCell.jp-mod-resizedCell
  .jp-CellResizeHandle::after {
  background: var(--jp-border-color0);
}

.jp-CellResizeHandle {
  display: none;
}

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Cell-Placeholder {
  padding-left: 55px;
}

.jp-Cell-Placeholder-wrapper {
  background: #fff;
  border: 1px solid;
  border-color: #e5e6e9 #dfe0e4 #d0d1d5;
  border-radius: 4px;
  -webkit-border-radius: 4px;
  margin: 10px 15px;
}

.jp-Cell-Placeholder-wrapper-inner {
  padding: 15px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body {
  background-repeat: repeat;
  background-size: 50% auto;
}

.jp-Cell-Placeholder-wrapper-body div {
  background: #f6f7f8;
  background-image: -webkit-linear-gradient(
    left,
    #f6f7f8 0%,
    #edeef1 20%,
    #f6f7f8 40%,
    #f6f7f8 100%
  );
  background-repeat: no-repeat;
  background-size: 800px 104px;
  height: 104px;
  position: absolute;
  right: 15px;
  left: 15px;
  top: 15px;
}

div.jp-Cell-Placeholder-h1 {
  top: 20px;
  height: 20px;
  left: 15px;
  width: 150px;
}

div.jp-Cell-Placeholder-h2 {
  left: 15px;
  top: 50px;
  height: 10px;
  width: 100px;
}

div.jp-Cell-Placeholder-content-1,
div.jp-Cell-Placeholder-content-2,
div.jp-Cell-Placeholder-content-3 {
  left: 15px;
  right: 15px;
  height: 10px;
}

div.jp-Cell-Placeholder-content-1 {
  top: 100px;
}

div.jp-Cell-Placeholder-content-2 {
  top: 120px;
}

div.jp-Cell-Placeholder-content-3 {
  top: 140px;
}

</style>
<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0 2px 1px -1px var(--jp-shadow-umbra-color),
    0 1px 1px 0 var(--jp-shadow-penumbra-color),
    0 1px 3px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0 3px 1px -2px var(--jp-shadow-umbra-color),
    0 2px 2px 0 var(--jp-shadow-penumbra-color),
    0 1px 5px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0 2px 4px -1px var(--jp-shadow-umbra-color),
    0 4px 5px 0 var(--jp-shadow-penumbra-color),
    0 1px 10px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0 3px 5px -1px var(--jp-shadow-umbra-color),
    0 6px 10px 0 var(--jp-shadow-penumbra-color),
    0 1px 18px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0 5px 5px -3px var(--jp-shadow-umbra-color),
    0 8px 10px 1px var(--jp-shadow-penumbra-color),
    0 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0 7px 8px -4px var(--jp-shadow-umbra-color),
    0 12px 17px 2px var(--jp-shadow-penumbra-color),
    0 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0 8px 10px -5px var(--jp-shadow-umbra-color),
    0 16px 24px 2px var(--jp-shadow-penumbra-color),
    0 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0 10px 13px -6px var(--jp-shadow-umbra-color),
    0 20px 31px 3px var(--jp-shadow-penumbra-color),
    0 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0 11px 15px -7px var(--jp-shadow-umbra-color),
    0 24px 38px 3px var(--jp-shadow-penumbra-color),
    0 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-inverse-border-color: var(--md-grey-600);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;
  --jp-ui-font-family: system-ui, -apple-system, blinkmacsystemfont, 'Segoe UI',
    helvetica, arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;
  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);
  --jp-content-link-color: var(--md-blue-900);
  --jp-content-font-family: system-ui, -apple-system, blinkmacsystemfont,
    'Segoe UI', helvetica, arial, sans-serif, 'Apple Color Emoji',
    'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: menlo, consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-900);
  --jp-brand-color1: var(--md-blue-700);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);
  --jp-accent-color0: var(--md-green-900);
  --jp-accent-color1: var(--md-green-700);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-900);
  --jp-warn-color1: var(--md-orange-700);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);
  --jp-error-color0: var(--md-red-900);
  --jp-error-color1: var(--md-red-700);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);
  --jp-success-color0: var(--md-green-900);
  --jp-success-color1: var(--md-green-700);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);
  --jp-info-color0: var(--md-cyan-900);
  --jp-info-color1: var(--md-cyan-700);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;
  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;
  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);
  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: var(--jp-code-font-family-default);
  --jp-cell-prompt-letter-spacing: 0;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);

  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;

  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0 0 2px 0 rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Statusbar specific styles */

  --jp-statusbar-height: 24px;

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-inverse-border-color);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: rgb(0, 54, 109);
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #a2f;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #a2f;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /*
    RTC user specific colors.
    These colors are used for the cursor, username in the editor,
    and the icon of the user.
  */

  --jp-collaborator-color1: #ffad8e;
  --jp-collaborator-color2: #dac83d;
  --jp-collaborator-color3: #72dd76;
  --jp-collaborator-color4: #00e4d0;
  --jp-collaborator-color5: #45d4ff;
  --jp-collaborator-color6: #e2b1ff;
  --jp-collaborator-color7: #ff9de6;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 250px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);

  /* Button colors */
  --jp-accept-color-normal: var(--md-blue-700);
  --jp-accept-color-hover: var(--md-blue-800);
  --jp-accept-color-active: var(--md-blue-900);
  --jp-warn-color-normal: var(--md-red-700);
  --jp-warn-color-hover: var(--md-red-800);
  --jp-warn-color-active: var(--md-red-900);
  --jp-reject-color-normal: var(--md-grey-600);
  --jp-reject-color-hover: var(--md-grey-700);
  --jp-reject-color-active: var(--md-grey-800);

  /* File or activity icons and switch semantic variables */
  --jp-jupyter-icon-color: #f37626;
  --jp-notebook-icon-color: #f37626;
  --jp-json-icon-color: var(--md-orange-700);
  --jp-console-icon-background-color: var(--md-blue-700);
  --jp-console-icon-color: white;
  --jp-terminal-icon-background-color: var(--md-grey-800);
  --jp-terminal-icon-color: var(--md-grey-200);
  --jp-text-editor-icon-color: var(--md-grey-700);
  --jp-inspector-icon-color: var(--md-grey-700);
  --jp-switch-color: var(--md-grey-400);
  --jp-switch-true-position-color: var(--md-orange-900);
}
</style>
<style type="text/css">
/* Force rendering true colors when outputing to pdf */
* {
  -webkit-print-color-adjust: exact;
}

/* Misc */
a.anchor-link {
  display: none;
}

/* Input area styling */
.jp-InputArea {
  overflow: hidden;
}

.jp-InputArea-editor {
  overflow: hidden;
}

.cm-editor.cm-s-jupyter .highlight pre {
/* weird, but --jp-code-padding defined to be 5px but 4px horizontal padding is hardcoded for pre.cm-line */
  padding: var(--jp-code-padding) 4px;
  margin: 0;

  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
  color: inherit;

}

.jp-OutputArea-output pre {
  line-height: inherit;
  font-family: inherit;
}

.jp-RenderedText pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
}

/* Hiding the collapser by default */
.jp-Collapser {
  display: none;
}

@page {
    margin: 0.5in; /* Margin for each printed piece of paper */
}

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }
}
</style>
<!-- Load mathjax -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-AMS_CHTML-full,Safe"> </script>
<!-- MathJax configuration -->
<script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: {
                    automatic: true
                    }
                }
            });

            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
<!-- End of mathjax configuration --><script type="module">
  document.addEventListener("DOMContentLoaded", async () => {
    const diagrams = document.querySelectorAll(".jp-Mermaid > pre.mermaid");
    // do not load mermaidjs if not needed
    if (!diagrams.length) {
      return;
    }
    const mermaid = (await import("https://cdnjs.cloudflare.com/ajax/libs/mermaid/10.7.0/mermaid.esm.min.mjs")).default;
    const parser = new DOMParser();

    mermaid.initialize({
      maxTextSize: 100000,
      maxEdges: 100000,
      startOnLoad: false,
      fontFamily: window
        .getComputedStyle(document.body)
        .getPropertyValue("--jp-ui-font-family"),
      theme: document.querySelector("body[data-jp-theme-light='true']")
        ? "default"
        : "dark",
    });

    let _nextMermaidId = 0;

    function makeMermaidImage(svg) {
      const img = document.createElement("img");
      const doc = parser.parseFromString(svg, "image/svg+xml");
      const svgEl = doc.querySelector("svg");
      const { maxWidth } = svgEl?.style || {};
      const firstTitle = doc.querySelector("title");
      const firstDesc = doc.querySelector("desc");

      img.setAttribute("src", `data:image/svg+xml,${encodeURIComponent(svg)}`);
      if (maxWidth) {
        img.width = parseInt(maxWidth);
      }
      if (firstTitle) {
        img.setAttribute("alt", firstTitle.textContent);
      }
      if (firstDesc) {
        const caption = document.createElement("figcaption");
        caption.className = "sr-only";
        caption.textContent = firstDesc.textContent;
        return [img, caption];
      }
      return [img];
    }

    async function makeMermaidError(text) {
      let errorMessage = "";
      try {
        await mermaid.parse(text);
      } catch (err) {
        errorMessage = `${err}`;
      }

      const result = document.createElement("details");
      result.className = 'jp-RenderedMermaid-Details';
      const summary = document.createElement("summary");
      summary.className = 'jp-RenderedMermaid-Summary';
      const pre = document.createElement("pre");
      const code = document.createElement("code");
      code.innerText = text;
      pre.appendChild(code);
      summary.appendChild(pre);
      result.appendChild(summary);

      const warning = document.createElement("pre");
      warning.innerText = errorMessage;
      result.appendChild(warning);
      return [result];
    }

    async function renderOneMarmaid(src) {
      const id = `jp-mermaid-${_nextMermaidId++}`;
      const parent = src.parentNode;
      let raw = src.textContent.trim();
      const el = document.createElement("div");
      el.style.visibility = "hidden";
      document.body.appendChild(el);
      let results = null;
      let output = null;
      try {
        let { svg } = await mermaid.render(id, raw, el);
        svg = cleanMermaidSvg(svg);
        results = makeMermaidImage(svg);
        output = document.createElement("figure");
        results.map(output.appendChild, output);
      } catch (err) {
        parent.classList.add("jp-mod-warning");
        results = await makeMermaidError(raw);
        output = results[0];
      } finally {
        el.remove();
      }
      parent.classList.add("jp-RenderedMermaid");
      parent.appendChild(output);
    }


    /**
     * Post-process to ensure mermaid diagrams contain only valid SVG and XHTML.
     */
    function cleanMermaidSvg(svg) {
      return svg.replace(RE_VOID_ELEMENT, replaceVoidElement);
    }


    /**
     * A regular expression for all void elements, which may include attributes and
     * a slash.
     *
     * @see https://developer.mozilla.org/en-US/docs/Glossary/Void_element
     *
     * Of these, only `<br>` is generated by Mermaid in place of `\n`,
     * but _any_ "malformed" tag will break the SVG rendering entirely.
     */
    const RE_VOID_ELEMENT =
      /<\s*(area|base|br|col|embed|hr|img|input|link|meta|param|source|track|wbr)\s*([^>]*?)\s*>/gi;

    /**
     * Ensure a void element is closed with a slash, preserving any attributes.
     */
    function replaceVoidElement(match, tag, rest) {
      rest = rest.trim();
      if (!rest.endsWith('/')) {
        rest = `${rest} /`;
      }
      return `<${tag} ${rest}>`;
    }

    void Promise.all([...diagrams].map(renderOneMarmaid));
  });
</script>
<style>
  .jp-Mermaid:not(.jp-RenderedMermaid) {
    display: none;
  }

  .jp-RenderedMermaid {
    overflow: auto;
    display: flex;
  }

  .jp-RenderedMermaid.jp-mod-warning {
    width: auto;
    padding: 0.5em;
    margin-top: 0.5em;
    border: var(--jp-border-width) solid var(--jp-warn-color2);
    border-radius: var(--jp-border-radius);
    color: var(--jp-ui-font-color1);
    font-size: var(--jp-ui-font-size1);
    white-space: pre-wrap;
    word-wrap: break-word;
  }

  .jp-RenderedMermaid figure {
    margin: 0;
    overflow: auto;
    max-width: 100%;
  }

  .jp-RenderedMermaid img {
    max-width: 100%;
  }

  .jp-RenderedMermaid-Details > pre {
    margin-top: 1em;
  }

  .jp-RenderedMermaid-Summary {
    color: var(--jp-warn-color2);
  }

  .jp-RenderedMermaid:not(.jp-mod-warning) pre {
    display: none;
  }

  .jp-RenderedMermaid-Summary > pre {
    display: inline-block;
    white-space: normal;
  }
</style>
<!-- End of mermaid configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">
<main>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=ddaefc09-7880-4000-9af9-7ca355e01585">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Import-Modules">Import Modules<a class="anchor-link" href="#Import-Modules">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=4ad5ba37-4c01-48b2-8b2e-f9de8b47db87">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [2]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Analysis</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>

<span class="c1"># Plot Visualization</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=6c9bc09b-73c8-4166-8566-2d310397dd1c">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Read-the-Data">Read the Data<a class="anchor-link" href="#Read-the-Data">¶</a></h4><ul>
<li>Casualty Data of Accidents in England and Wales in 2022</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=88c0ed0f-64f1-4e71-a027-f2970445e410">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [3]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s2">"Data/dft-road-casualty-statistics-casualty-2022.csv"</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="p">{</span><span class="s2">"accident_index"</span><span class="p">:</span> <span class="nb">str</span><span class="p">,</span> <span class="s2">"accident_reference"</span><span class="p">:</span> <span class="nb">str</span><span class="p">})</span>
<span class="n">df</span><span class="o">.</span><span class="n">sample</span><span class="p">(</span><span class="mi">5</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[3]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>accident_index</th>
<th>accident_year</th>
<th>accident_reference</th>
<th>vehicle_reference</th>
<th>casualty_reference</th>
<th>casualty_class</th>
<th>sex_of_casualty</th>
<th>age_of_casualty</th>
<th>age_band_of_casualty</th>
<th>casualty_severity</th>
<th>pedestrian_location</th>
<th>pedestrian_movement</th>
<th>car_passenger</th>
<th>bus_or_coach_passenger</th>
<th>pedestrian_road_maintenance_worker</th>
<th>casualty_type</th>
<th>casualty_home_area_type</th>
<th>casualty_imd_decile</th>
<th>lsoa_of_casualty</th>
</tr>
</thead>
<tbody>
<tr>
<th>81894</th>
<td>2022371149895</td>
<td>2022</td>
<td>371149895</td>
<td>2</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>38</td>
<td>7</td>
<td>3</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>5</td>
<td>E01030030</td>
</tr>
<tr>
<th>123394</th>
<td>202254C277322</td>
<td>2022</td>
<td>54C277322</td>
<td>2</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>27</td>
<td>6</td>
<td>3</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>5</td>
<td>1</td>
<td>6</td>
<td>E01015478</td>
</tr>
<tr>
<th>27236</th>
<td>2022031156596</td>
<td>2022</td>
<td>031156596</td>
<td>2</td>
<td>1</td>
<td>1</td>
<td>2</td>
<td>-1</td>
<td>-1</td>
<td>3</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>9</td>
<td>1</td>
<td>5</td>
<td>E01019182</td>
</tr>
<tr>
<th>55047</th>
<td>2022161215683</td>
<td>2022</td>
<td>161215683</td>
<td>2</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>42</td>
<td>7</td>
<td>3</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>3</td>
<td>1</td>
<td>1</td>
<td>E01012849</td>
</tr>
<tr>
<th>80563</th>
<td>2022361191233</td>
<td>2022</td>
<td>361191233</td>
<td>4</td>
<td>2</td>
<td>1</td>
<td>1</td>
<td>59</td>
<td>9</td>
<td>3</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>3</td>
<td>4</td>
<td>E01026280</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=82e6487a-1849-4d9d-86da-a9afefa4f8bf">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Convert-All-Data-Types-to-String-and-Replace-'-1's-with-NaN">Convert All Data Types to String and Replace '-1's with NaN<a class="anchor-link" href="#Convert-All-Data-Types-to-String-and-Replace-'-1's-with-NaN">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=03b4f019-4ea7-4ca8-8bd3-57c8ac8b78f9">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [4]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">str</span><span class="p">)</span>
<span class="n">df</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s1">'-1'</span><span class="p">,</span> <span class="n">pd</span><span class="o">.</span><span class="n">NA</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">df</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[4]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>accident_index</th>
<th>accident_year</th>
<th>accident_reference</th>
<th>vehicle_reference</th>
<th>casualty_reference</th>
<th>casualty_class</th>
<th>sex_of_casualty</th>
<th>age_of_casualty</th>
<th>age_band_of_casualty</th>
<th>casualty_severity</th>
<th>pedestrian_location</th>
<th>pedestrian_movement</th>
<th>car_passenger</th>
<th>bus_or_coach_passenger</th>
<th>pedestrian_road_maintenance_worker</th>
<th>casualty_type</th>
<th>casualty_home_area_type</th>
<th>casualty_imd_decile</th>
<th>lsoa_of_casualty</th>
</tr>
</thead>
<tbody>
<tr>
<th>count</th>
<td>135480</td>
<td>135480</td>
<td>135480</td>
<td>135480</td>
<td>135480</td>
<td>135480</td>
<td>134403</td>
<td>132351</td>
<td>132351</td>
<td>135480</td>
<td>135477</td>
<td>135479</td>
<td>134855</td>
<td>135411</td>
<td>135220</td>
<td>135451</td>
<td>122184</td>
<td>121526</td>
<td>116799</td>
</tr>
<tr>
<th>unique</th>
<td>106004</td>
<td>1</td>
<td>106004</td>
<td>17</td>
<td>19</td>
<td>3</td>
<td>3</td>
<td>102</td>
<td>11</td>
<td>3</td>
<td>11</td>
<td>10</td>
<td>4</td>
<td>6</td>
<td>3</td>
<td>22</td>
<td>3</td>
<td>10</td>
<td>31104</td>
</tr>
<tr>
<th>top</th>
<td>2022010356595</td>
<td>2022</td>
<td>010356595</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>18</td>
<td>6</td>
<td>3</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>9</td>
<td>1</td>
<td>2</td>
<td>E01019456</td>
</tr>
<tr>
<th>freq</th>
<td>16</td>
<td>135480</td>
<td>16</td>
<td>80304</td>
<td>104962</td>
<td>89770</td>
<td>82746</td>
<td>3407</td>
<td>27952</td>
<td>107949</td>
<td>116153</td>
<td>116153</td>
<td>112590</td>
<td>133568</td>
<td>132645</td>
<td>72759</td>
<td>98949</td>
<td>15159</td>
<td>65</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=2a8b7e28-24d2-45f1-a2ab-18f6a4f464e6">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Casualty-Class-(casualty_class)">Casualty Class (casualty_class)<a class="anchor-link" href="#Casualty-Class-(casualty_class)">¶</a></h4><ul>
<li>Driver / Rider (1)</li>
<li>Passenger (2)</li>
<li>Pedestrian (3)</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=a4df7e56-8cb4-4c8e-8c90-4348baa90ff2">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [51]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'casualty_class'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'1'</span><span class="p">:</span> <span class="s1">'Driver/Rider'</span><span class="p">,</span>
    <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'Passenger'</span><span class="p">,</span>
    <span class="s1">'3'</span><span class="p">:</span> <span class="s1">'Pedestrian'</span>
<span class="p">}</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="n">_id</span><span class="p">])</span>
<span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'proportion'</span><span class="p">]</span> <span class="o">*</span> <span class="mi">100</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'tab20c'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">types</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">],</span> <span class="n">labels</span><span class="o">=</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">radius</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">center</span><span class="o">=</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span>
       <span class="n">wedgeprops</span><span class="o">=</span><span class="p">{</span><span class="s2">"linewidth"</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span> <span class="s2">"edgecolor"</span><span class="p">:</span> <span class="s2">"white"</span><span class="p">},</span> <span class="n">frame</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="n">centre_circle</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">Circle</span><span class="p">((</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span> <span class="mf">0.6</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">gca</span><span class="p">()</span><span class="o">.</span><span class="n">add_artist</span><span class="p">(</span><span class="n">centre_circle</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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Ra9evfDFF1+ck+XsojAajc3eJ0kSZLnlGzparVZERkZi9erV57wvMDCw6c8+Pj4tfk6iy8GCIrpMPj4+SExMbPa2bdu2QZZlvPHGG9DpGucgff311+d8bGxsLB588EE8+OCDePbZZ/Hxxx/j0UcfBdBYNpMmTcKkSZMwcOBAPP3003j99deRnp6OefPmITw8HP7+l7cxYqdOnWC327Fjxw706tULQOO1pPLy8qbHpKeno7CwEAaDAR06dLis1yFyBs7iI3KixMRE2Gw2/POf/8Thw4fx2Wef4YMPPmj2mD/96U/46aefcOTIEWzfvh2rVq1C586dAQAvvvgiFi5ciJycHOzduxc//PBD0/smTJiA0NBQjBo1CmvXrsWRI0ewevVqPPbYYzh27FiL8qWkpGDYsGH44x//iM2bN2PHjh344x//CLPZDEmSAADDhg1D3759MXr0aCxbtgy5ubnYsGEDnn/+eWzdutWJny2ii2NBETlRWloa/vGPf+Bvf/sbunXrhi+++AKvvvpqs8c4HA5MmTIFnTt3RkZGBpKTk5tm+JlMJjz77LNITU3FoEGDoNfr8dVXXwEALBYL1qxZg/bt2+PWW29F586dce+996Kurq5VI6p///vfaNeuHQYNGoQxY8bg/vvvh5+fX9NUcUmSsHjxYgwaNAj33HMPkpOTMX78eOTl5aFdu3ZO+kwRXRp31CXSuGPHjiE2NhYrVqzA0KFDRcchasKCItKYlStXwmq1onv37igoKMC0adNw/PhxZGVlnTPBgkgkTpIg0hibzYbnnnsOhw8fhp+fH/r164cvvviC5USqwxEUERGpEidJEBGRKrGgiIhIlVhQRESkSiwoIiJSJRYUERGpEguKiIhUiQVFRESqxIIiIiJVYkEREZEqsaCIiEiVWFBERKRKLCgiIlIlFhQREakSC4qIiFSJBUVERKrEgiIiIlViQRERkSqxoIiISJVYUEREpEosKCIiUiUWFBERqRILioiIVIkFRUREqsSCIiIiVfp/KDEPjHi4fRMAAAAASUVORK5CYII="/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=257eda3c-4df4-4966-8909-94f73465ab55">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [52]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">statistics</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[52]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>casualty_class</th>
<th>proportion</th>
<th>percentage</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>Driver/Rider</td>
<td>0.662607</td>
<td>66.260703</td>
</tr>
<tr>
<th>1</th>
<td>Passenger</td>
<td>0.194737</td>
<td>19.473723</td>
</tr>
<tr>
<th>2</th>
<td>Pedestrian</td>
<td>0.142656</td>
<td>14.265574</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=4ea36da3-d9fa-41fd-81b5-fdd5ec3888d2">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [19]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/casualty_class.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=c62439ce-f88b-430c-a046-151e1fd959a8">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Pedestrian-Location-(pedestrian_location)">Pedestrian Location (pedestrian_location)<a class="anchor-link" href="#Pedestrian-Location-(pedestrian_location)">¶</a></h4><ul>
<li>Crossing on pedestrian crossing facility (1)</li>
<li>Crossing in zig-zag approach lines (2)</li>
<li>Crossing in zig-zag exit lines (3)</li>
<li>Crossing elsewhere within 50m of pedestrian crossing (4)</li>
<li>In carriageway, crossing elsewhere (5)</li>
<li>On footway or verge (6)</li>
<li>On refuge, central island or central reservation (7)</li>
<li>In centre of carriageway - not on refuge, island or central reservation (8)</li>
<li>In carriageway, not crossing (9)</li>
<li>Unknown or other (10)</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=8885d6bc-d821-45a9-a36b-f3cce77d3366">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [26]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'pedestrian_location'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'1'</span><span class="p">:</span> <span class="s1">'Crossing on pedestrian crossing facility'</span><span class="p">,</span>
    <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'Crossing in zig-zag approach lines'</span><span class="p">,</span>
    <span class="s1">'3'</span><span class="p">:</span> <span class="s1">'Crossing in zig-zag exit lines'</span><span class="p">,</span>
    <span class="s1">'4'</span><span class="p">:</span> <span class="s1">'Crossing elsewhere within 50m of pedestrian crossing'</span><span class="p">,</span>
    <span class="s1">'5'</span><span class="p">:</span> <span class="s1">'In carriageway, crossing elsewhere'</span><span class="p">,</span>
    <span class="s1">'6'</span><span class="p">:</span> <span class="s1">'On footway or verge'</span><span class="p">,</span>
    <span class="s1">'7'</span><span class="p">:</span> <span class="s1">'On refuge, central island or central reservation'</span><span class="p">,</span>
    <span class="s1">'8'</span><span class="p">:</span> <span class="s1">'In centre of carriageway - not on refuge, island or central reservation'</span><span class="p">,</span>
    <span class="s1">'9'</span><span class="p">:</span> <span class="s1">'In carriageway, not crossing'</span><span class="p">,</span>
    <span class="s1">'10'</span><span class="p">:</span> <span class="s1">'Unknown or other'</span>
<span class="p">}</span>

<span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s1">'0'</span><span class="p">,</span> <span class="n">pd</span><span class="o">.</span><span class="n">NA</span><span class="p">)</span>
<span class="n">df2</span> <span class="o">=</span> <span class="n">df2</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">ascending</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="n">_id</span><span class="p">])</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'viridis'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">statistics</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">barh</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'count'</span><span class="p">],</span> <span class="n">color</span><span class="o">=</span><span class="n">colors</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">'Number of Casualties'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">grid</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA+8AAAGwCAYAAADYPVQuAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjguMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/H5lhTAAAACXBIWXMAAA9hAAAPYQGoP6dpAADKIUlEQVR4nOzde1zP9///8du7g0pKiqmIHCqJyGnDKJOJsdkBMxuZwzaaGWGbzcLQHOYwm50+YsbYnIc5TiE+zplNJCQbZjOn2KdS/f7w6/X11hFN4X69XN4X3q/D8/V4PV+v97v34/V8vp4vU1ZWVhYiIiIiIiIiUmJZFHcAIiIiIiIiIpI/Je8iIiIiIiIiJZySdxEREREREZESTsm7iIiIiIiISAmn5F1ERERERESkhFPyLiIiIiIiIlLCKXkXERERERERKeGsijsAERERuXOZmZmcOnUKBwcHTCZTcYcjIiIihZCVlcXly5dxd3fHwiL/tnUl7yIiIveBU6dO4eHhUdxhiIiIyG04efIklStXzncZJe8iIiL3AQcHBwCOHz+Os7NzMUdzb0tPT2fdunU8/vjjWFtbF3c49zTVZdFRXRYd1WXRUV3euUuXLuHh4WH8Hc+PkncREZH7QHZXeQcHBxwdHYs5mntbeno6pUuXxtHRUT9G75DqsuioLouO6rLoqC6LTmFuedOAdSIiIiIiIiIlnJJ3ERERERERkRJOybuIiIiIiIhICafkXURERERERKSEU/IuIiIiIiIiUsIpeRcREREREREp4ZS8i4iIiIiIiJRwSt5FRERERERESjgl7yIiIiIiIiIlnJJ3ERERERERkRJOybuIiIiIiIhICafkXURERERERKSEU/IuIiIiIiIiUsIpeRcREREREREp4ayKOwAREREpOplnW5CZfq24w7inZV6zAT4g848GZFqlFnc49zTVZdFRXRYd1WXReZDq0sI1obhDUMu7iIiIiIiISEmn5F1ERERERESkhFPyLiIiIiIiIlLCKXkXERERERERKeGUvIuIiIiIiIiUcEreRUREREREREo4Je8iIiIiIiIiJZySdxEREREREZESTsm7iJQoSUlJmEwm4uLiijsUucns2bNxcnIq7jAAMJlMLFu27K5vV+eniIiIFBcl7yL3udDQUDp16lTcYRSah4cHp0+fpk6dOsUdityka9euJCQk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y4thw4bRt29f4/z86quv6N27NwAHDx7Ez8+P+Ph4atWqRZ8+fbC0tOTzzz83iyMwMJArV65ga2ub67lfmPVuFBERwahRo3LU3/z58yldunSudSsiIiIly9WrV3nhhRe4ePEijo6O+S6rlneRB5C/v7/Zezc3N6PL983Onj3LqVOnaN26dZ7lbdiwgfHjx3Po0CEuXbrEtWvX+N///sfVq1eNJKJUqVI5tgvXu6sX5JNPPmHWrFkkJyfzzz//kJaWZiT2Fy9e5I8//qBJkybG8paWljRs2JDMzEwAEhMTuXr1ao6eBWlpaQQEBADQokULLl++zL59+9i2bRuBgYEEBQUZFzRiYmIYOnSose6ePXuIiIhg//79nD9/3thWcnIytWvXxt3dnSeeeIJZs2bRpEkTfvjhB1JTU+ncuXOB+5stLi6OFi1a5NvyXbduXbN7pePj46lXr56RuAM0b96czMxMDh8+TMuWLQkNDaVt27a0adOG4OBgunTpgpubG3C9pbxPnz7MnTuX4OBgOnfuTI0aNfLcvqenp5G4g/m5dOzYMdLT082OTdmyZY3u/XnZv38/sbGxRus9XL8gc/M5lS00NJQ2bdrg4+NDSEgIHTp04PHHHzfKSklJwcXFxWydf/75x7j9IDAwkP/85z9kZGQQExPD448/jqurK9HR0fj7+5OYmEhQUJDZ+jeey9l1d/bsWWrVqsX+/fv5+eefzS70ZGVlkZmZyfHjx/H19QVynvuFXS/b22+/zeDBg433ly5dwsPDg6C6E3B2yv0WAymcaxk2bIh7j+D6Y7CyTC14BcmT6rLoqC6Ljuqy6DxIdWlRce+/Um52z7nCUPIu8gC6ORk0mUxG8nmzggYoS0pKokOHDrz22muMHTsWZ2dntm7dSu/evUlLSzMSLTs7uxytooBZkpmbBQsWEB4ezuTJk2natCkODg5MnDiRHTt25LvejbLv9161ahWVKlUym5fdGuvk5ES9evWIjo5m+/bttGnThpYtWxojrB85csRoqc7umt62bVvmzZtHhQoVSE5Opm3btqSlpRll9+nTh5deeokpU6YQFRVF165db6lFtDCDwxVUf7mJiopi4MCBrFmzhoULF/Luu++yfv16HnnkESIiInjhhRdYtWoVP/74I++//z4LFizg6aefzrWsWzmXCislJYVRo0bxzDPP5Jh3c+szQIMGDTh+/Dg//vgjGzZsoEuXLgQHB7No0SJSUlJwc3MjOjo6x3rZ9++3bNmSy5cvs3fvXjZv3sy4ceNwdXUlMjKSevXq4e7ujpeXl9m6N+539nmdvd8pKSm88sorDBw4MMc2q1SpYvz/5mNX2PWy2djYmPUmyGZlmYq1lZL3onC9Lu/vH6N3i+qy6Kgui47qsug8CHVpkU9jyp3Ir5HmZkreRSRfDg4OeHp6snHjRrN7yLPt2bOHzMxMJk+ebIwe/9133xXZ9mNjY2nWrBn9+/c3pmW3mML1ltyKFSuya9cuWrZsCVxvpb3xvuobB8nLrat4tsDAQDZt2sTOnTuNCxG+vr6MHTsWNzc3vL29ATh06BDnzp0jMjLSGMgse8CzG7Vv3x57e3tmzpzJmjVr2Lx58y3tu7+/P3PmzCE9Pb3QX+y+vr7Mnj2bK1euGMlhbGwsFhYWZi3eAQEBBAQE8Pbbb9O0aVPmz59vDNLm7e2Nt7c3b775Jt26dSMqKirP5D0/1atXx9raml27dhnJ58WLF0lISDCOVW4aNGjA4cOHCz02AFzv7t+1a1e6du3Kc889R0hICH///TcNGjTgzJkzWFlZ4enpmeu6Tk5O+Pv7M2PGDKytralVqxYPPfQQXbt2ZeXKlfmeM3nFf/DgwVuK/07WExERkQeDRpsXkQJFREQwefJkpk+fzpEjR9i7dy8ff/wxcP3e4fT0dD7++GOOHTvG3Llz+eyzz4ps215eXuzevZu1a9eSkJDAe++9x65du8yWef311xk/fjzLly/n8OHDvPHGG5w/f95oEXVwcCA8PJw333yTOXPmcPToUWMf5syZY5QTFBTE2rVrsbKyolatWsa0efPmmSVwVapUoVSpUsY+r1ixgjFjxuSI3dLSktDQUN5++228vLzM7rcvjLCwMC5dusTzzz/P7t27OXLkCHPnzuXw4cN5rtO9e3dsbW3p2bMnv/zyC5s2beL111/npZdeomLFihw/fpy3336b7du3c+LECdatW8eRI0fw9fXln3/+ISwsjOjoaE6cOEFsbCy7du3K0V27sBwcHOjZsydDhw5l06ZN/Prrr/Tu3RsLC4tce2FkGzlyJF9//TWjRo3i119/JT4+ngULFvDuu+/muvxHH33Et99+y6FDh0hISOD777/H1dUVJycngoODadq0KZ06dWLdunUkJSWxbds2RowYYXbB5ebjnH3hZuHChbecvA8fPpxt27YRFhZGXFwcR44cYfny5WZPaCjK9UREROTBoORdRArUs2dPpk6dyqeffoqfnx8dOnTgyJEjANSrV4+PPvqIDz/8kDp16jBv3jyzx3TdqVdeeYVnnnmGrl278vDDD3Pu3DmzVni4nvR069aNHj160LRpU8qUKUPbtm3NuliPGTOG9957j/Hjx+Pr60tISAirVq2iWrVqxjItWrQgMzPTLFnLHuDvxnueK1SowOzZs/n++++pXbs2kZGROR4Lly379oFevXrlmBcaGprjXuobubi48NNPP5GSkkJgYCANGzbkyy+/zLcVvnTp0qxdu5a///6bxo0b89xzz9G6dWtmzJhhzD906BDPPvss3t7e9OvXjwEDBvDKK69gaWnJuXPn6NGjB97e3nTp0oV27drlOihaYX300Uc0bdqUDh06EBwcTPPmzfH19c21+3u2tm3bsnLlStatW0fjxo155JFHmDJlClWrVs11eQcHByZMmECjRo1o3LgxSUlJrF692rhIsHr1alq2bEmvXr3w9vbm+eef58SJE1SsWNEoIzAwMMdxzu3YF4a/vz8xMTEkJCTQokULAgICGDlyJO7u7v/KeiIiIvJg0GjzInLfyczMxNfXly5duuTaIn43bdmyhdatW3Py5EmzZBGuJ4ytWrUiIiKieIIrBleuXKFSpUpMnjzZGK1disalS5coW7YsZw/64lJO97zfifRrNqzZ8wEhDd+97+/h/LepLouO6rLoqC6LzoNUlxauCf9Kudl/vzXavIg8ELK7fwcGBpKamsqMGTM4fvw4L7zwQrHFlJqayp9//klERASdO3fOkbhfvHiRo0ePsmrVqmKK8O7Yt28fhw4dokmTJly8eJHRo0cD8NRTTxVzZCIiIiL3FnWbF5F7noWFBbNnz6Zx48Y0b96cAwcOsGHDhtu+V7sofPvtt1StWpULFy4wYcKEHPPLli3Lb7/9RpkyZYohurtr0qRJ1KtXj+DgYK5cucKWLVsoX758cYclIiIick9Ry7uI3PM8PDyIjY0t7jDMhIaGEhoaWtxhFLuAgAD27NlT3GGIiIiI3PPU8i4iIiIiIiJSwil5FxERERERESnhlLyLiIiIiIiIlHC6511EROQ+YvHQFixcXIo7jHuaRXo6sBqLinuxsLYu7nDuaarL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Yc6dO2cMJngngoKC+P7771mxYgX169fnscceY+fOnfmu06BBA7777jsWLFhAnTp1GDlyJKNHjyY0NBQg33PN0dGRzZs30759e7y9vXn33XeZPHky7dq1u634LS0tWbZsGSkpKTRu3Jg+ffowYsQIIP/z8GYWFhYsWLCAPXv2UKdOHd58800mTpxotkypUqVYt24dDz30EO3bt6du3bpERkaajTFwK0aPHk1SUhI1atSgQoUKZvN69+5NWloaL7/88m2VLSIiIvcnU9ad3kwqIsL1keOzn2V+t+4PhuvPeW/VqhXnz5/P8/59eXDExsby6KOPkpiYWKjBAkuiuXPn8uabb3Lq1CnjAlRhXLp0ibJly/Ld3nrYO+me9zuRlWHDtV9HYuU3+r6+T/tueFDqsn21X/71baSnp7N69Wrat2+ve4vvkOqy6Kgu71z23++LFy/i6OiY77IasE5EbsvXX39N9erVqVSpEvv372f48OF06dLlribuIkuXLqVMmTJ4eXmRmJjIG2+8QfPmze/JxP3q1aucPn2ayMhIXnnllVtK3EVEROT+p27zInJbzpw5w4svvoivry9vvvkmnTt35osvvijusOQBc/nyZQYMGECtWrUIDQ2lcePGLF++vLjDui0TJkygVq1auLq68vbbbxd3OCIiIlLCqOVdRG7LsGHDGDZsWHGHQVBQ0B0/Sk7uXT169KBHjx7FHUaRiIiIICIiorjDEBERkRJKLe8iIiIiIiIiJZySdxEREREREZESTsm7iIiIiIiISAmn5F1ERERERESkhNOAdSIiIveRx6psxMXFpbjDuKelp6ez+tfVPF71v3pu8R1SXYqIFB21vIuIiIiIiIiUcEreRUREREREREo4Je8iIiIiIiIiJZySdxEREREREZESTsm7iIiIiIiISAmn0eZFRETuIyN/6Y+Vo67N3wnLTCsCeY7hP79MhsW14g7nnjUt4NviDkFE5L6iv+4iIiIiIiIiJZySdxEREREREZESTsm7iIiIiIiISAmn5F1ERERERESkhFPyLiIiIiIiIlLCKXkXERERERERKeGUvIuIiIiIiIiUcEreRUREREREREo4Je8iIiIiIiIiJZySdxGR+0xWVhb9+vXD2dkZk8lEXFxccYckIiIiIndIybuISDE4efIkL7/8Mu7u7pQqVYqqVavyxhtvcO7cuTsue82aNcyePZuVK1dy+vRp6tSpUwQRQ1BQEIMGDSqSskRERETk1ih5FxG5y44dO0ajRo04cuQI3377LYmJiXz22Wds3LiRpk2b8vfff99R+UePHsXNzY1mzZrh6uqKlZVVEUV+/0hPT78r28nKyuLatWt3ZVsiIiJyf1PyLiJylw0YMIBSpUqxbt06AgMDqVKlCu3atWPDhg38/vvvjBgxwljW09OTcePG8fLLL+Pg4ECVKlX44osv8iw7NDSU119/neTkZEwmE56engCkpqYycOBAHnroIWxtbXn00UfZtWuX2boxMTE0adIEGxsb3NzceOutt4zEMzQ0lJiYGKZNm4bJZMJkMpGUlESjRo2YNGmSUUanTp2wtrYmJSUFgN9++w2TyURiYiIAc+fOpVGjRjg4OODq6soLL7zA2bNngeuJbs2aNc3KA4iLizMr42aZmZmMHj2aypUrY2NjQ/369VmzZo0xPykpCZPJxMKFCwkMDMTW1pZ58+blKOeFF16ga9euZtPS09MpX748X3/9tbGt8ePHU61aNezs7KhXrx6LFi0ylo+OjsZkMvHjjz/SsGFDbGxs2Lp1K5cvX6Z79+7Y29vj5ubGlClTcvRkSE1NJTw8nEqVKmFvb8/DDz9MdHR0rvucvfylS5fMXgCWmVZ6FcFLdXnnr/T0dONCWfb/9bqzl+pSdVkSX6rLoqnDwlBzjIjIXfT333+zdu1axo4di52dndk8V1dXunfvzsKFC/n0008xmUwATJ48mTFjxvDOO++waNEiXnvtNQIDA/Hx8clR/rRp06hRowZffPEFu3btwtLSEoBhw4axePFi5syZQ9WqVZkwYQJt27YlMTERZ2dnfv/9d9q3b09oaChff/01hw4dom/fvtja2hIREcG0adNISEigTp06jB49GoAKFSoQGBhIdHQ04eHhZGVlsWXLFpycnNi6dSshISHExMRQqVIlatasCVz/4z5mzBh8fHw4e/YsgwcPJjQ0lNWrV2MymXj55ZeJiooiPDzc2KeoqChatmxplJHbPk+ePJnPP/+cgIAAZs2axZNPPsmvv/6Kl5eXsdxbb73F5MmTCQgIwNbWNkc53bt3p3PnzqSkpFCmTBkA1q5dy9WrV3n66acBGD9+PN988w2fffYZXl5ebN68mRdffNGoixu3NWnSJKpXr065cuUYPHgwsbGxrFix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5R2u3/eemZlplqgHBQWRkZFBUFCQMa1ChQrMnj2b77//ntq1axMZGZnjsXDZevfuTVpaGr169Spw3wYOHMjgwYMZMmQIdevWZc2aNaxYsSLXEdoLo3v37hw8eJBKlSrluJd+zJgxvPfee4wfPx5fX19CQkJYtWoV1apVy7fMjz76iKZNm9KhQweCg4Np3rw5vr6+ZqPeR0VF0aNHD4YMGYKPjw+dOnVi165deY43ICIiIg8WjTYvIiIlzpYtW2jdujUnT56kYsWKxR1Okbty5QqVKlVi8uTJRu+HO3Xp0iXKli1L/+guGm3+DllmWhH423PEVF6kAevuwLSAb0lPT2f16tW0b99eg1ndIdVl0VFdFh3V5Z3L/vut0eZFROSekpqayp9//klERASdO3e+bxL3ffv2cejQIZo0acLFixcZPXo0gPE4OREREZGC6NK8iIiUGN9++y1Vq1blwoULTJgwobjDKVKTJk2iXr16BAcHc+XKFbZs2UL58uWLOywRERG5R6jlXURESozQ0FBCQ0OLO4wiFxAQwJ49e4o7DBEREbmHqeVdREREREREpIRT8i4iIiIiIiJSwil5FxERERERESnhdM+7iIjIfWR0nU9xcXEp7jDuaenp6az+bTUf+s/So49ERKTEUMu7iIiIiIiISAmn5F1ERERERESkhFPyLiIiIiIiIlLCKXkXERERERERKeGUvIuIiIiIiIiUcEreRUREREREREo4PSpORETkPvJE9Idk2uvP+50olWXJUBrRasNo0kwZxR1OkdkZMq64QxARkTuglncRERERERGREk7Ju4iIiIiIiEgJp+RdREREREREpIRT8i4iIiIiIiJSwil5FxERERERESnhlLyLiIiIiIiIlHBK3kVERERERERKOCXvIiIiIiIiIiWckncRkSKUlJSEyWQiLi6uuEORYhQdHY3JZOLChQvFHYqIiIjcJ5S8i0iJFhoaSqdOnYo7jELz8PDg9OnT1KlTp7hDuW+YTCaWLVtW3GHckmbNmnH69GnKli1b3KGIiIjIfULJu4jILcrIyCAzMzPH9LS0NCwtLXF1dcXKyqoYIpPCSktL+1fLL1WqFK6urphMpn91OyIiIvLgUPIuIveUoKAgBg4cyLBhw3B2dsbV1ZWIiIgC15s1axZ+fn7Y2Njg5uZGWFiYMe+jjz6ibt262Nvb4+Hh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Rw+8vb3p0qUL7dq1M0Zx9vf3JyYmhoSEBFq0aEFAQAAjR440BvqC6xcSWrRogclk4tFHHzXWc3R0pFGjRrfcXXfMmDG89957jB8/Hl9fX0JCQli1ahXVqlUr8vXuJPa+ffvi4+NDo0aNqFChQr4jjP8bxowZQ8OGDXn44YdZvnw5CxcuNBt8sVmzZsyfP58vvvjCeGzesmXLivwZ7yaTieXLl1OuXDlatmxJcHAw1atXZ+HChbdVXmRkJJGRkdSrV4+tW7eyYsUKypcvD4C7uzuxsbFkZGTw+OOPU7duXQYNGoSTk5ORoE+cOJEWLVrQsWNHgoODefTRR3Pc713QZyQjI4MBAwYY55G3t7cxGFylSpUYNWoUb731FhUrVryliyFPPvkkb775JmFhYdSvX59t27bx3nvv3VY93cjb25t169axf/9+mjRpQtOmTVm+fHmeTzfI3o/Vq1ezc+dO6tWrx6uvvkrv3r2NAfUcHR3ZvHkz7du3x9vbm3fffZfJkyfTrl07SpcuzaFDh4xHcfbr148BAwYYAx/ejq+//pqKFSvSsmVLnn76aWMU/vy+60REROTBYcq61dHNRIrZvHnz6NWrFxcvXizUfa4i94qkpCSqVavGvn37zB7rJg+m3377DQ8PDzZs2GA8OSA/ly5domzZsjTsO55MS402X1h7Z76ZY1p6ejqrV6+mffv2GoDpDqkui47qsuioLouO6vLOZf/9vnjxYo4BfG+m0ealxPv666+pXr06lSpVYv/+/cYzrZW4i8j95KeffiIlJYW6dety+vRphg0bhqenZ6EHIhQREZH7m5J3KfHOnDnDyJEjOXPmDG5ubnTu3DnPZz2LiNyr0tPTeeeddzh27BgODg40a9aMefPmqSVDREREACXvcg8YNmwYw4YNK+4wRP51np6e6E6mB1fbtm1p27ZtcYchIiIiJZQGrBMREREREREp4ZS8i4iIiIiIiJRwSt5FRERERERESjjd8y4iInIfWTu+Ly4uLsUdhoiIiBQxtbyLiIiIiIiIlHBK3kVERERERERKOCXvIiIiIiIiIiWckncRERERERGREk7Ju4iIiIiIiEgJp+RdREREREREpITTo+JERETuI8+9NJNMSuW7TMzqYXcpGhERESkqankXERERERERKeGUvIuIiIiIiIiUcEreRUREREREREo4Je8iIiIi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GT///DP09PSqlXVyckJkZCSWLVsGe3t7xMXFYenSpQ2uMygoCGPGjIGvry9cXFygoaFR4+McT+vcuTN++OEHxMfHw97eHqGhoVi4cKHUZHX19fnnnyMoKAihoaGwtbXFyJEjxWfy6/O9qY+FCxciLy8P7du3r/Mxja+//hp3795F586dMWbMGAQGBooTR76Iur6fmpqaOHz4MLy9vdGhQwd89tlniIiIEGeJnzhxIjZv3oyYmBg4ODjAzc0NsbGxMDc3r7NuiUSCUaNG4ezZs9VG7t977z188sknCAgIQKdOnfDbb7+JExFWGTZsGLy8vNCvXz+0adMG27dvr1aHqqoq9u3bhzt37qBbt24YPnw4BgwYgHXr1r1A1IiIiOhNIhFe1sOdRCRKS0tDr169kJOTI5Xo1yYmJgZLlizBhQsX+EwREVVTVFQELS0t9B24CBV1TFh3aHfIS2rVq6m0tBS7d+8WJzSkxmMsmw5j2XQYy6bDWL64qt/f9+/fr3Pwhc+8E70EiYmJUFdXh5WVFXJycjB9+nS4urrWO3EHKl/ttGTJEv7HSERERET0BmLyTvQSPHjwALNnz0Z+fj5at24Nd3f3Bs9W/eOPPzZT64iIiIiISNYxeSd6CcaOHYuxY8e2dDOIiIiIiOgVxQnriIiIiIiIiGQck3ciIiIiIiIiGcfknYiIiIiIiEjG8Zl3IiKi18hPW6dCT0+vpZtBRERETYwj70REREREREQyjsk7ERERERERkYxj8k5EREREREQk45i8ExEREREREck4Ju9EREREREREMo7JOxEREREREZGM46viiIiIXiP/7RsOlEn/et+TtbSFWkNERERNhSPvRERERERERDKOyTsRERERERGRjGPyTkRERERERCTjmLwTERERERERyTgm70REREREREQyjsk7ERERERERkYxj8k5EREREREQk45i8ExEREREREck4Ju9EJHP69u2LGTNmNHs9ZmZmiIqKarbjh4WFoVOnTs12fHoxEokEO3fubNA+z35nGnMMIiIiosaQb+kGEFHLKiwsxOLFi/Hrr7/ir7/+Qtu2bdGpUyfMmDEDAwYMaJE2JSQkQEFBodnrSU9Ph5qaWrMdPzg4GNOmTWu241PLKygogI6OTks3g4iIiN4ATN6J3mB5eXlwdXWFtrY2VqxYAQcHB5SWlmLfvn3w9/fH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PsP5ghjLpsNYNh3Gsukwli+u6vc3Z5snojfGli1bYGFhgXbt2uHs2bOYPXs2RowYIVOJ+7Vr17B//364ubmhpKQE69atw9WrV8XXoTWXAwcOoLi4GA4ODigoKEBISAjMzMye+z56IiIiIpI9TN6J6LVQWFiI0NBQFBYWwtDQEB988AEWL17c0s2S0qpVK8TGxiI4OBiCIMDe3h7Jycm1Tt7WFEpLS/Hpp5/iypUr0NDQQM+ePREXF8cr5ERERESvECbvRPRaCAkJQUhISEs3o1bGxsbVZuh/GTw9PeHp6dnkx63rqSszM7M6yxARERFR/XDCOiIiIiIiIiIZx+SdiIiIiIiISMYxeSciIiIiIiKScUzeiYiIiIiIiGQcJ6wjIiJ6jXyXOgd6enot3QwiIiJqYhx5JyIiIiIiIpJxTN6JiIiIiIiIZByTdyIiIiIiIiIZx+SdiIiIiIiISMYxeSciIiIiIiKScZxtnoiI6DXyH+MpwL+V/06q+LFlG0NERERNhiPvRERERERERDKOyTsRERERERGRjGPyTkRERERERCTjmLwTERERERERyTgm70REREREREQyjsk7ERERERERkYxj8k5EREREREQk45i8ExEREREREck4Ju9EREREREREMo7JOxFRA/Tt2xczZsxo9nrMzMwQFRXVbMcPCwtDp06dmu34siwvLw8SiQQZGRkN2i82Nhba2tri8pscQyIiInr5mLwTkcwqLCzEtGnTYGFhASUlJRgbG8PHxwcpKSkt1qaEhAQsWrSo2etJT0/H5MmTm+34wcHBLRrHlmRsbIyCggLY29sDAFJTUyGRSHDv3r0GHedNjiERERG9fPIt3QAioprk5eXB1dUV2traWLFiBRwcHFBaWop9+/bB398fFy9erHG/0tJSKCgoNFu7dHV1m+3YT2vTpk2zHl9dXR3q6urNWoeskpOTg4GBwQsf502OIREREb18HHknIpnk5+cHiUSCEydOYNiwYejQoQPs7Owwc+ZM/P7772I5iUSCDRs24L333oOamhoWL14MANiwYQPat28PRUVFWFtbY+vWreI+giAgLCwMJiYmUFJSgpGREQIDA8Xt69evh5WVFZSVlaGvr4/hw4eL2569bd7MzAxLlizBhAkToKGhARMTE3z11VdSffntt9/QqVMnKCsro2vXrti5c2edt20/e9u8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gC1btkBfXx99+vTB0KFDMWnSJGhoaNRa78SJE7F582bExMTAwcEBbm5uiI2Nhbm5Of7991/897//xbhx4+Dj4wMAmDx5Mvr164cxY8bUOLrerl07LFiwAHPmzIG+vj4CAgLqjG9jxcTEYOzYsQgKCoK1tTWGDBmC9PR0cfb98vJy+Pv7w9bWFl5eXujQoYPUa/CIiIjozSURGjozFBERvZC4uDiMHz8e9+/ff6HXkjWniooK2NraYsSIEVi0aNFLq/fPP/+EsbExkpOTMWDAgJdW7+ugqKgIWlpacFcZDvxbuS6p4seWbdQrqrS0FLt374a3tzcnYHpBjGXTYSybDmPZdBjLF1f1+/v+/fs1vhnnabxtnoiomW3ZsgUWFhZo164dzp49i9mzZ2PEiBEylbhfu3YN+/fvh5ubG0pKSrBu3TpcvXoVH374YbPWe+DAARQXF8PBwQEFBQUICQmBmZnZc99HT0RERPSmYvJORNTMCgsLERoaisLCQhgaGuKDDz7A4sWLW7pZUlq1aoXY2FgEBwdDEATY29sjOTm52Z+3Li0txaeffoorV65AQ0MDPXv2RFxcHK/eExERET2DyTsRUTMLCQlBSEhISzejVsbGxtVm6H8ZPD094enp+dLrJSIiInrVcMI6IiIiIiIiIhnH5J2IiIiIiIhIxjF5JyIiIiIiIpJxfOadiIjoNRJ/fSP09PRauhlERETUxDjyTkRERERERCTjmLwTERERERERyTgm70REREREREQyjsk7ERERERERkYxj8k5EREREREQk45i8ExEREREREck4Ju9EREREREREMo7JOxEREREREZGMY/JOREREREREJOOYvBMRERERERHJOCbvRERERERERDKOyTsRERERERGRjGPyTkRERERERCTjmLwTERERERERyTgm70REREREREQyTr6lG0BEREQvThAEAMCDBw+goKDQwq15tZWWluLRo0coKipiLF8QY9l0GMumw1g2HcbyxRUVFQH4/9/jtWHyTkRE9Bq4ffs2AMDc3LyFW0JEREQN9eDBA2hpadVahsk7ERHRa0BXVxcAkJ+fX+cvf6pdUVERjI2Ncf36dWhqarZ0c15pjGXTYSybDmPZdBjLFycIAh48eAAjI6M6yzJ5JyIieg20alU5jY2Wlhb/gGoimpqajGUTYSybDmPZdBjLpsNYvpj6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iytXrmDr1q3VJtKbMWMG9u3bh6tXr+L06dM4ePCgeNGiR48eUFVVxaefforc3Fxs27YNsbGxUvtbWVkhISEBGRkZOHv2LD788MM672owMzNDSkoKCgsLn/t6wAULFmDp0qVYs2YNLl26hMzMTMTExCAyMhJA5Sz627dvx8WLF3Hp0iX8+OOPMDAwqDY7PtHrhMk7EREREcmUhQsXVksAbW1tsX79ekRHR8PJyQknTpyocSb2xgoPD0d4eDicnJxw9OhR7Nq1C61btwYAcbS8vLwc77zzDhwcHDBjxgxoa2tLPV9fH4GBgZg5cyaCgoLg4OCAvXv3YteuXbCysmrQcSwsLHD69Gn069cPQUFBsLe3h4eHB1JSUrBhwwYAgJOTEyIjI7Fs2TLY29sjLi6u2uvUysvL4e/vD1tbW3h5eaFDhw7iK9l0dXXx3XffYffu3XBwcMD27durvbouMjISOjo66NmzJ3x8fODp6YnOnTvX2vaIiAgkJSXB2NgYzs7ONZaZOHEiNm/ejJiYGDg4OMDNzQ2xsbHiyLuGhgaWL1+Orl27olu3bsjLy8Pu3bsbfD6IXiUSoSEzXhARERERERHRS8dLU0REREREREQyjsk7ERERERERkYxj8k5EREREREQk45i8ExEREREREck4Ju9EREREREREMo7JOxEREREREZGMY/JOREREREREJOOYvBMRERERERHJOCbvRERERERERDKOyTsRERERERGRjGPyTkRERERERCTj/g96YRMkrlZh3gAAAABJRU5ErkJggg=="/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=2dd21cf5-7be9-4511-86be-63732c9f0296">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [27]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/pedestrian_location.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=21f2f3d6-59c1-4060-b311-c0087f5f71f1">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Pedestrian-Movement-(pedestrian_movement)">Pedestrian Movement (pedestrian_movement)<a class="anchor-link" href="#Pedestrian-Movement-(pedestrian_movement)">¶</a></h4><ul>
<li>Crossing from driver's nearside (1)</li>
<li>Crossing from nearside - masked by parked or stationary vehicle (2)</li>
<li>Crossing from driver's offside (3)</li>
<li>Crossing from offside - masked by  parked or stationary vehicle (4)</li>
<li>In carriageway, stationary - not crossing  (standing or playing) (5)</li>
<li>In carriageway, stationary - not crossing  (standing or playing) - masked by parked or stationary vehicle (6)</li>
<li>Walking along in carriageway, facing traffic (7)</li>
<li>Walking along in carriageway, back to traffic (8)</li>
<li>Unknown or other (9)</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=20abca27-b3fd-4e35-b544-3d8f6435893a">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [23]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'pedestrian_movement'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'1'</span><span class="p">:</span> <span class="s2">"Crossing from driver's nearside"</span><span class="p">,</span>
    <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'Crossing from nearside - masked by parked or stationary vehicle'</span><span class="p">,</span>
    <span class="s1">'3'</span><span class="p">:</span> <span class="s2">"Crossing from driver's offside"</span><span class="p">,</span>
    <span class="s1">'4'</span><span class="p">:</span> <span class="s1">'Crossing from offside - masked by parked or stationary vehicle'</span><span class="p">,</span>
    <span class="s1">'5'</span><span class="p">:</span> <span class="s1">'In carriageway, stationary - not crossing (standing or playing)'</span><span class="p">,</span>
    <span class="s1">'6'</span><span class="p">:</span> <span class="s1">'In carriageway, stationary - not crossing (standing or playing) - masked by parked or stationary vehicle'</span><span class="p">,</span>
    <span class="s1">'7'</span><span class="p">:</span> <span class="s1">'Walking along in carriageway, facing traffic'</span><span class="p">,</span>
    <span class="s1">'8'</span><span class="p">:</span> <span class="s1">'Walking along in carriageway, back to traffic'</span><span class="p">,</span>
    <span class="s1">'9'</span><span class="p">:</span> <span class="s1">'Unknown or other'</span>
<span class="p">}</span>

<span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s1">'0'</span><span class="p">,</span> <span class="n">pd</span><span class="o">.</span><span class="n">NA</span><span class="p">)</span>
<span class="n">df2</span> <span class="o">=</span> <span class="n">df2</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="n">_id</span><span class="p">])</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'viridis'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">statistics</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">barh</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'count'</span><span class="p">],</span> <span class="n">color</span><span class="o">=</span><span class="n">colors</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">yticks</span><span class="p">(</span><span class="n">rotation</span><span class="o">=</span><span class="mi">20</span><span class="p">,</span> <span class="n">ha</span><span class="o">=</span><span class="s1">'right'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">'Number of Casualties'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">grid</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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"/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=9cd25c5b-1b90-43cd-bbe2-0994842b21c7">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [25]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/pedestrian_movement.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=8436e715-36a4-4020-aab8-b7368dc4eb99">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Car-Passenger-(car_passenger)">Car Passenger (car_passenger)<a class="anchor-link" href="#Car-Passenger-(car_passenger)">¶</a></h4><ul>
<li>Front seat passenger (1)</li>
<li>Rear seat passenger (2)</li>
<li>Unknown (9)</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=4939f848-349a-4d80-8493-a4b627a77fbd">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [28]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'car_passenger'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'1'</span><span class="p">:</span> <span class="s1">'Front seat passenger'</span><span class="p">,</span>
    <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'Rear seat passenger'</span><span class="p">,</span>
    <span class="s1">'9'</span><span class="p">:</span> <span class="s1">'Unknown'</span>
<span class="p">}</span>

<span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s1">'0'</span><span class="p">,</span> <span class="n">pd</span><span class="o">.</span><span class="n">NA</span><span class="p">)</span>
<span class="n">df2</span> <span class="o">=</span> <span class="n">df2</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="n">_id</span><span class="p">])</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'Set2'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">types</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="s1">'proportion'</span><span class="p">],</span> <span class="n">labels</span><span class="o">=</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">radius</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">center</span><span class="o">=</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span>
       <span class="n">wedgeprops</span><span class="o">=</span><span class="p">{</span><span class="s2">"linewidth"</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span> <span class="s2">"edgecolor"</span><span class="p">:</span> <span class="s2">"white"</span><span class="p">},</span> <span class="n">frame</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="n">centre_circle</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">Circle</span><span class="p">((</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span> <span class="mf">0.6</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">gca</span><span class="p">()</span><span class="o">.</span><span class="n">add_artist</span><span class="p">(</span><span class="n">centre_circle</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAcoAAAGFCAYAAAB9krNlAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjguMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/H5lhTAAAACXBIWXMAAA9hAAAPYQGoP6dpAABLe0lEQVR4nO3deXxU1cE+8Ofe2TOZ7PueQBIg7ALKImEJggsignsrvK+2dUGqFKu/Wqu41IpLrdraV21R0dZdawVURDZR2fclkABJgITs+zpzz++PyGgEQhKSOTO5z/fzyQeT2Z5M4n1yzz33XEUIIUBERERnpMoOQERE5M1YlERERO1gURIREbWDRUlERNQOFiUREVE7WJRERETtYFESERG1g0VJRETUDhYlERFRO1iURERE7WBREhERtYNFSURE1A4WJRERUTtYlERERO1gURIREbWDRUlERNQOFiUREVE7WJRERETtYFESERG1g0VJRETUDhYlERFRO1iURERE7WBREhERtYNFSURE1A4WJRERUTtYlERERO1gURIREbWDRUlERNQOFiUREVE7WJRERETtYFESERG1g0VJRETUDhYlERFRO1iURERE7WBREhERtYNFSURE1A4WJRERUTtYlERERO1gURIREbWjU0U5d+5cKIpy2kdOTk5P5QMAKIqCjz/+uEdfoyOSkpLw3HPPyY5BREQeZOzsA6ZNm4YlS5a0+Vp4ePhp92tubobZbO56Mup1+DtBRL6o00OvFosFUVFRbT4MBgMmTJiAefPm4e6770ZYWBimTp0KAFi7di1GjRoFi8WC6Oho3H///XA6ne7nmzBhAubPn4/f/va3CAkJQVRUFB5++GH37UlJSQCAmTNnQlEU9+c/1dzcjHnz5iE6OhpWqxWJiYl44okn3LdXVlbi1ltvRXh4OAICAjBp0iTs3LnTfXtubi5mzJiByMhI+Pv7Y+TIkfjyyy/b5MzLy8M999zj3pM+G0VR8NJLL+HSSy+FzWZDSkoK3n///Tb3ue+++5CWlgY/Pz+kpKTgwQcfREtLi/v2nTt3YuLEiXA4HAgICMAFF1yALVu2AADy8vIwffp0BAcHw263IyMjA8uXL3c/ds+ePbj00kvh7++PyMhI/PznP0dpaWmH33MAOHDgAMaNGwer1YoBAwbgyy+/PG3PvqCgANdeey2CgoIQEhKCGTNm4OjRo+7b586di6uuugqPP/44YmJikJ6eftb3jIjIW3XrMcrXX38dZrMZGzZswN///nccP34cl112GUaOHImdO3fipZdewj/+8Q889thjpz3Obrdj48aNWLx4MR555BGsXLkSALB582YAwJIlS1BYWOj+/Keef/55fPLJJ3j33XeRnZ2Nt956q02pXnPNNSguLsaKFSuwdetWDB8+HJMnT0Z5eTkAoLa2FpdddhlWrVqF7du3Y9q0aZg+fTry8/MBAB9++CHi4uLwyCOPoLCwEIWFhe2+Fw8++CBmzZqFnTt34qabbsL111+P/fv3u293OBx47bXXsG/fPvzlL3/BK6+8gj//+c/u22+66SbExcVh8+bN2Lp1K+6//36YTCYAwJ133ommpiasW7cOu3fvxpNPPgl/f38ArX8QTJo0CcOGDcOWLVvw2Wef4eTJk7j22ms7/J67XC5cddVV8PPzw8aNG/Hyyy/jgQceaPP4lpYWTJ06FQ6HA+vXr8eGDRvg7++PadOmobm52X2/VatWITs7GytXrsSnn37a7ntGROSVRCfMmTNHGAwGYbfb3R+zZ88WQgiRmZkphg0b1ub+v/vd70R6errQNM39tb/+9a/C399fuFwu9+PGjRvX5nEjR44U9913n/tzAOKjjz5qN9tdd90lJk2a1Oa1Tlm/fr0ICAgQjY2Nbb7ep08f8X//939nfc6MjAzxwgsvuD9PTEwUf/7zn9vNcSrvbbfd1uZrF154obj99tvP+pinnnpKXHDBBe7PHQ6HeO21185430GDBomHH374jLc9+uij4pJLLmnztYKCAgFAZGdnCyHO/Z6vWLFCGI1GUVhY6L595cqVbX4OS5cuPe1n29TUJGw2m/j888+FEK2/L5GRkaKpqems3zcRkbfr9DHKiRMn4qWXXnJ/brfb3f99wQUXtLnv/v37MXr06DbDlGPHjkVtbS2OHTuGhIQEAMDgwYPbPC46OhrFxcWdyjV37lxMmTIF6enpmDZtGq644gpccsklAFqHMWtraxEaGtrmMQ0NDcjNzQXQukf58MMPY9myZSgsLITT6URDQ4N7j7KzRo8efdrnO3bscH/+zjvv4Pnnn0dubi5qa2vhdDoREBDgvn3BggW49dZbsXTpUmRlZeGaa65Bnz59AADz58/H7bffji+++AJZWVmYNWuW+z3cuXMn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L34Bu92OOXPmuDM+8MADePrpp5GamooHHngAN9xwA3JycmA0GrFhwwbcdtttePLJJ3HllVfiyy+/xIMPPtjme1y/fj1uvvlmPP/887j44ouRm5uLX/7ylwCAhx56yH2/hx9+GH/605/w3HPPwWiUWFeCiDzK6XKJpmanaG5xyo4izZw5c4TBYBB2u11YLBYBQKiqKt5//30hhBCNjY3Cz89PfPPNN20ed8stt4gbbrjhrM975513ilmzZrV5ncjISNHU1NRuHofDIV577bUz3nbLLbeIX/7yl22+tn79eqGqqmhoaDjjYzZv3iwAiJqaGiGEEKtXrxYAREVFRbs5lixZIgCI7777zv21/fv3CwBi48aNZ31cRkaGeOGFF4QQQnzwwQciICBAVFdXn3a/rVu3CgDi6NGjZ3yePn36iH/9619tvvboo4+K0aNHCyGEOHLkiAAgXn31Vffte/fuFQDE/v37hRBCXHfddeLyyy9v8xw33XSTCAwMdH8+efJk8cc//rHNfZYuXSqio6PdnwMQd99991m/Z09iURKRx82ZM0dkZWWJQ4cOiR07dog5c+aIW265xX37nj17BABht9vbfJhMJjFq1Cj3/V588UUxfPhwERYW5r595MiRp73OuTz00EPCaDSKyZMniyeeeELk5OS4bxsxYoQwm81tcvj5+QkAYt++fUIIIbZs2SKuuOIKER8fL/z9/d237927VwjRuaI0Go3C5XK1+XpQUJC7yGtqasRvfvMb0a9fPxEYGCjsdrtQVVXce++9QgghqqurxaBBg0RYWJj42c9+Jt58801RV1cnhBDC6XSKyZMnC4fDIWbPni1efvllUV5eLoQQora2VgAQNputzfdqsVhERESEEOKHoty0aZM7W3l5uQAg1q5dK4QQYujQoWLRokVt8v/lL39pU5RhYWHCarW2eR2r1SoAuLMCEG+++eY5fnKewaFXIpLCbrejb9++AIB//vOfGDJkCP7xj3/glltuQW1tLQBg2bJliI2NbfM4i8UCAHj77bexcOFCPPPMMxg9ejQcDgeeeuopbNy48bTXOZeHH34YN954I5YtW4YVK1bgoYcewttvv42ZM2eitrYWv/rVrzB//vzTHpeQkIC6ujpMnToVU6dOxVtvvYXw8HDk5+dj6tSpaG5u7tJ7056FCxdi5cqVePrpp9G3b1/YbDbMnj3b/VoOhwPbtm3DmjVr8MUXX+APf/gDHn74YWzevBlBQUFYuXIlvvnmG3zxxRd44YUX8MADD2Djxo3w8/MD0Hp88cILL2zzmgZD29OGfjyp5tTl0zSt4zPIa2trsWjRIlx99dWn3fbjWc8d+dl5AouSiKRTVRW/+93vsGDBAtx4440YMGAALBYL8vPzkZmZecbHbNiwAWPGjMEdd9zh/lpubm6XM6SlpSEtLQ333HMPbrjhBixZsgQzZ87E8OHDsW/fPnep/9Tu3btRVlaGP/3pT4iPjweANhOBALhn2rpc515u0el0YsuWLRg1ahQAIDs7G5WVlejfvz+A1u977ty5mDlzJoDW0jl69Gib5zAajcjKykJWVhYeeughBAUF4auvvsLVV18NRVEwduxYjB07Fn/4wx+QmJiIjz76CAsWLEBMTAwOHz6Mm266qeNv3E+kp6dj8+bNbb7208+HDx+O7Ozss76n3oZFSURe4ZprrsG9996Lv/71r1i4cCEWLlyIe+65B5qmYdy4caiqqsKGDRsQEBCAOXPmIDU1FW+88QY+//xzJCcnY+nSpdi8eTOSk5M79boNDQ249957MXv2bCQnJ+PYsWPYvHkzZs2aBQC47777cNFFF2HevHm49dZbYbfbsW/fPqxcuRIvvvgiEhISYDab8cILL+C2227Dnj178Oijj7Z5jcTERCiKgk8//RSXXXYZbDYb/P1PnywGtO6t3XXXXXj++edhNBoxb948XHTRRe7iTE1NxYcffojp06dDURQ8+OCDbfbmPv30Uxw+fBjjx49HcHAwli9fDk3TkJ6ejo0bN2LVqlW45JJLEBERgY0bN6KkpMRdwosWLcL8+fMRGBiIadOmoampCVu2bEFFRQUWLFjQoffzrrvuwvjx4/Hss89i+vTp+Oqrr7BixYo2F+7+wx/+gCuuuAIJCQmYPXs2VFXFzp07sWfPHjz22GMd/+F5iuyxXyLSnzlz5ogZM2ac9vUnnnhChIeHi9raWqFpmnjuuedEenq6MJlMIjw8XEydOtV9LKyxsVHMnTtXBAYGiqCgIHH77beL+++/XwwZMuScr/NjTU1N4vrrrxfx8fHCbDaLmJgYMW/evDYTdTZt2iSmTJki/P39hd1uF4MHDxaPP/64+/Z//etfIikpSVgsFjF69GjxySefCABi+/bt7vs88sgjIioqSiiKIubMmXPGLEuWLBGBgYHigw8+ECkpKcJisYisrCyRl5fnvs+RI0fExIkThc1mE/Hx8eLFF18UmZmZ4te//rUQonWiUWZmpggODhY2m00MHjxYvPPOO0IIIfbt2yemTp0qwsPDhcViEWlpae5JQKe89dZbYujQocJsNovg4GAxfvx48eGHH7pf+6ffV0VFhQAgVq9e7f7ayy+/LGJjY4XNZhNXXXWVeOyxx0RUVFSb1/nss8/EmDFjhM1mEwEBAWLUqFHi5Zdfdt8OQHz00Udn/bl5ElfmISLyEq+99hruvvtuVFZWyo7SrX7xi1/gwIED7tNUfA2HXomIqFs9/fTTmDJlCux2O1asWIHXX3+9zcIFvoZFSURE3WrTpk1YvHgxampqkJKSgueffx633nqr7FhdxqFXIiKidnCtVyIionawKImIiNrBoiQiImoHi5KIiKgdLEoiIqJ2sCiJiIjawaIkIiJqB4uSiIioHSxKIiKidrAoiYiI2sGiJCIiageLkoiIqB0sSiIionawKImIiNrBoiQiImoHi5KIiKgdLEoiIqJ2sCiJiIjawaIkIiJqB4uSiIioHSxKIiKidrAoiYiI2sGiJCIiageLkoiIqB0sSiIionawKImIiNrBoiQiImoHi5KIiKgdLEoiIqJ2sCiJiIjawaIkIiJqB4uSiIioHSxKIiKidrAoiYiI2sGiJCIiageLkoiIqB0sSiIionb8f4O+AVH7IortAAAAAElFTkSuQmCC"/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=a45fbaa6-22fc-46b3-a12e-dd060abc149a">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [29]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/car_passenger.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=30f8e023-e171-4707-93b2-2fd77e246aee">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Bus-or-Coach-Passenger-Type-(bus_or_coach_passenger)">Bus or Coach Passenger Type (bus_or_coach_passenger)<a class="anchor-link" href="#Bus-or-Coach-Passenger-Type-(bus_or_coach_passenger)">¶</a></h4><ul>
<li>Boarding (1)</li>
<li>Alighting (2)</li>
<li>Standing passenger (3)</li>
<li>Seated passenger (4)</li>
<li>Unknown (9)</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=572da8b2-0a0a-413d-b4ae-b0b1fe8fd1e8">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [49]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'bus_or_coach_passenger'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'1'</span><span class="p">:</span> <span class="s1">'Boarding'</span><span class="p">,</span>
    <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'Alighting'</span><span class="p">,</span>
    <span class="s1">'3'</span><span class="p">:</span> <span class="s1">'Standing passenger'</span><span class="p">,</span>
    <span class="s1">'4'</span><span class="p">:</span> <span class="s1">'Seated passenger'</span><span class="p">,</span>
    <span class="s1">'9'</span><span class="p">:</span> <span class="s1">'Unknown'</span>
<span class="p">}</span>

<span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s1">'0'</span><span class="p">,</span> <span class="n">pd</span><span class="o">.</span><span class="n">NA</span><span class="p">)</span>
<span class="n">df2</span> <span class="o">=</span> <span class="n">df2</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="n">_id</span><span class="p">])</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'Set2'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">types</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="s1">'proportion'</span><span class="p">],</span> <span class="n">labels</span><span class="o">=</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">radius</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">center</span><span class="o">=</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span>
       <span class="n">wedgeprops</span><span class="o">=</span><span class="p">{</span><span class="s2">"linewidth"</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span> <span class="s2">"edgecolor"</span><span class="p">:</span> <span class="s2">"white"</span><span class="p">},</span> <span class="n">frame</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="n">centre_circle</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">Circle</span><span class="p">((</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span> <span class="mf">0.6</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">gca</span><span class="p">()</span><span class="o">.</span><span class="n">add_artist</span><span class="p">(</span><span class="n">centre_circle</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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"/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=6e1f9f71-4790-4aeb-a507-0f9cdb3abc19">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [50]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/bus_or_coach_passenger.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=46420d51-1ad6-4405-ba0f-a0c62e631078">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Casualty-Sex-(sex_of_casualty)">Casualty Sex (sex_of_casualty)<a class="anchor-link" href="#Casualty-Sex-(sex_of_casualty)">¶</a></h4><ul>
<li>Male (1)</li>
<li>Female (2)</li>
<li>Unknown (9)</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=1a27872f-8a31-4702-bb0f-eee565d6b700">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [32]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'sex_of_casualty'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'1'</span><span class="p">:</span> <span class="s1">'Male'</span><span class="p">,</span>
    <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'Female'</span><span class="p">,</span>
<span class="p">}</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s1">'9'</span><span class="p">,</span> <span class="n">pd</span><span class="o">.</span><span class="n">NA</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="n">_id</span><span class="p">])</span>
<span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'proportion'</span><span class="p">]</span> <span class="o">*</span> <span class="mi">100</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'Set2'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">types</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">],</span> <span class="n">labels</span><span class="o">=</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">radius</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">center</span><span class="o">=</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span>
       <span class="n">wedgeprops</span><span class="o">=</span><span class="p">{</span><span class="s2">"linewidth"</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span> <span class="s2">"edgecolor"</span><span class="p">:</span> <span class="s2">"white"</span><span class="p">},</span> <span class="n">frame</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="n">centre_circle</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">Circle</span><span class="p">((</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span> <span class="mf">0.6</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">gca</span><span class="p">()</span><span class="o">.</span><span class="n">add_artist</span><span class="p">(</span><span class="n">centre_circle</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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CfX19cjJycHdd9+NeDx+3myhUAjl5eXYuHHjOW/Lz88f3x+QJoWlQEQpjY2NOHLkyLTflrplyxbce++9uPPOOwGMXfRbWloumqOrqwt2ux21tbXTmoUujqVARCnf/OY3ceutt6K6uhp33303VFXFnj17sH//fnznO9+Z9OedPXs2nnvuOdx2221QFAXf+MY3UqOI87nuuuuwcuVK3HHHHfj+97+POXPmoLOzEy+88ALuvPNOrFixYtJZ6OJ49xERpdx44414/vnnsX79elxyySW4/PLL8YMf/AA1NTVT+ryPPfYYAoEAVq1ahdtuuw033ngjGhsbL/j+iqLgxRdfxOrVq3Hfffdhzpw5+MQnPoGTJ0+m1jAoPXjMBRERpXCkQEREKSwFIiJKYSkQEVEKS4GIiFJYCkRElMJSICKiFJYCERGlsBSIiCiFpUBERCksBSIiSmEpEBFRCkuBiIhSWApERJTCUiAiohSWAhERpbAUiIgohaVAREQpLAUiIkphKRARUQpLgYiIUlgKRESUwlIgIqIUlgIREaWwFIiIKIWlQEREKSwFIiJKYSkQEVEKS4GIiFJYCkRElMJSICKiFJYCERGlsBSIiCiFpUBERCksBSIiSmEpEBFRCkuBiIhSWApERJTy/wF+m2ykzw8atgAAAABJRU5ErkJggg=="/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=49a0e13a-6823-409f-a02d-ca8420df290d">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [33]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/casualty_sex.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=32aa4ea3-e99d-439a-920a-1fa97cf799c7">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Casualty-Age-(age_of_casualty)">Casualty Age (age_of_casualty)<a class="anchor-link" href="#Casualty-Age-(age_of_casualty)">¶</a></h4>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=e6da4e8d-97ef-4ce1-ae3b-1b2d9f2073f5">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [34]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'age_of_casualty'</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="n">variable</span><span class="p">)</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'viridis'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">statistics</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'count'</span><span class="p">],</span> <span class="n">color</span><span class="o">=</span><span class="n">colors</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">grid</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">"Casualty Age"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">"Number of Casualties"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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"/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=d5e4cd4a-a3ec-4cd3-9b02-6a4c44ec68ab">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [35]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/age_of_casualty.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=89ddd66a-c19a-4c5a-a07c-fc100d7d6bde">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Casualty-Age-Band-(age_band_of_casualty)">Casualty Age Band (age_band_of_casualty)<a class="anchor-link" href="#Casualty-Age-Band-(age_band_of_casualty)">¶</a></h4><table>
<thead>
<tr>
<th>Age Band</th>
<th>1</th>
<th>2</th>
<th>3</th>
<th>4</th>
<th>5</th>
<th>6</th>
<th>7</th>
<th>8</th>
<th>9</th>
<th>10</th>
<th>11</th>
</tr>
</thead>
<tbody>
<tr>
<td>Age Interval</td>
<td>0-5</td>
<td>6-10</td>
<td>11-15</td>
<td>16-20</td>
<td>21-25</td>
<td>26-35</td>
<td>36-45</td>
<td>46-55</td>
<td>56-65</td>
<td>66-75</td>
<td>76-120</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=9bcd3cac-26cd-444c-8151-9e7cae5d9339">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [36]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'age_band_of_casualty'</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="n">variable</span><span class="p">)</span>
<span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'proportion'</span><span class="p">]</span> <span class="o">*</span> <span class="mi">100</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'viridis'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">statistics</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">],</span> <span class="n">labels</span><span class="o">=</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">radius</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">center</span><span class="o">=</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span>
       <span class="n">wedgeprops</span><span class="o">=</span><span class="p">{</span><span class="s2">"linewidth"</span><span class="p">:</span> <span class="mf">0.3</span><span class="p">,</span> <span class="s2">"edgecolor"</span><span class="p">:</span> <span class="s2">"black"</span><span class="p">},</span> <span class="n">frame</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="n">centre_circle</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">Circle</span><span class="p">((</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span> <span class="mf">0.6</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">gca</span><span class="p">()</span><span class="o">.</span><span class="n">add_artist</span><span class="p">(</span><span class="n">centre_circle</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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"/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=c38af351-7b34-487e-8811-d714a3fdd2e8">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [37]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/casualty_age_band.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=d672bbfa-ebcb-4a7a-bd4a-b1aa2f3963f9">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Casualty-Severity-(casualty_severity)">Casualty Severity (casualty_severity)<a class="anchor-link" href="#Casualty-Severity-(casualty_severity)">¶</a></h4><ul>
<li>Fatal (1)</li>
<li>Serious (2)</li>
<li>Slight (3)</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=7bf0ebdc-6833-4f83-8234-75d2e4ea1774">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [38]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'casualty_severity'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'1'</span><span class="p">:</span> <span class="s1">'Fatal'</span><span class="p">,</span>
    <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'Serious'</span><span class="p">,</span>
    <span class="s1">'3'</span><span class="p">:</span> <span class="s1">'Slight'</span>
<span class="p">}</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="n">_id</span><span class="p">])</span>
<span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'proportion'</span><span class="p">]</span> <span class="o">*</span> <span class="mi">100</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'hot'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mf">0.7</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">types</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">],</span> <span class="n">labels</span><span class="o">=</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">radius</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">center</span><span class="o">=</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span>
       <span class="n">wedgeprops</span><span class="o">=</span><span class="p">{</span><span class="s2">"linewidth"</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span> <span class="s2">"edgecolor"</span><span class="p">:</span> <span class="s2">"black"</span><span class="p">},</span> <span class="n">frame</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="n">centre_circle</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">Circle</span><span class="p">((</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span> <span class="mf">0.6</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">gca</span><span class="p">()</span><span class="o">.</span><span class="n">add_artist</span><span class="p">(</span><span class="n">centre_circle</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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7206kPiYCkQ6XvJTaHwNGprfMutNJ3KX4N4QOxXioyB2MgSKTCcSAVQgkmu2DcmPoGFOc6m8Dnae3SzJtOD+ED2++e0bEDncdCKRnVKBiFl2GpoWOiOTxjcguRjSX5pOlTtWEUSOccoi0lwaQd0aVtxBBSL5J13hHO6Y/BCaFjf/+iOw60wnaxurCEIHQGTgV4URPtQ5SkbEhVQg4g627Vx/srlYkh9CahWkV0N6DbDjtlYjAl0g1NcpitABzq/Dze+DOmtKvEUFIu5n25CpbC6T1ZBZ89Wvt/zeBsjUAw1gb/W2yyvqLed+8oHir96sYgiUbPdxMQS7OjfsCvV1PhbxCRWI+JudBjI4RZJxyggbrJimlkT2QAUiIiJZ0UssERHJigpERESyogIREZGsqEBERCQrKhAREcmKCkRERLKiAhERkayoQEREJCsqEBERyYoKREREsqICERGRrKhAREQkKyoQERHJigpERESyogIREZGsqEBERCQrKhAREcmKCkRERLKiAhERkayoQEREJCsqEBERyYoKREREsqICERGRrKhAREQkKyoQERHJigpERESyogIREZGsqEBERCQrKhAREcmKCkRERLKiAhERkayoQEREJCsqEBERyYoKREREsqICERGRrKhAREQkKyoQERHJigpERESyogIREZGsqEBERCQrKhAREcmKCkRERLKiAhERkayoQEREJCsqEBERycr/BzQrz3Wp7x/hAAAAAElFTkSuQmCC"/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=578b2567-2e55-4ec8-8cad-f1fb83e020a3">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [39]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/casualty_severity.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=f5834344-84b6-4a45-872b-06e14dfdc08b">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3 id="Casualty-Type-(casualty_type)">Casualty Type (casualty_type)<a class="anchor-link" href="#Casualty-Type-(casualty_type)">¶</a></h3>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=f95d81c1-87a2-465d-a376-d5935b0d7b08">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [43]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'casualty_type'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'0'</span><span class="p">:</span> <span class="s1">'Not-a-Vehicle'</span><span class="p">,</span> <span class="s1">'1'</span><span class="p">:</span> <span class="s1">'Cyclist'</span><span class="p">,</span> <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'Motorcycle1'</span><span class="p">,</span> <span class="s1">'3'</span><span class="p">:</span> <span class="s1">'Motorcycle2'</span><span class="p">,</span> <span class="s1">'4'</span><span class="p">:</span> <span class="s1">'Motorcycle3'</span><span class="p">,</span> <span class="s1">'5'</span><span class="p">:</span> <span class="s1">'Motorcycle4'</span><span class="p">,</span>\
    <span class="s1">'8'</span><span class="p">:</span> <span class="s1">'Taxi'</span><span class="p">,</span> <span class="s1">'9'</span><span class="p">:</span> <span class="s1">'Car'</span><span class="p">,</span> <span class="s1">'10'</span><span class="p">:</span> <span class="s1">'Minibus'</span><span class="p">,</span> <span class="s1">'11'</span><span class="p">:</span> <span class="s1">'Bus'</span><span class="p">,</span> <span class="s1">'16'</span><span class="p">:</span> <span class="s1">'Horse'</span><span class="p">,</span> <span class="s1">'17'</span><span class="p">:</span> <span class="s1">'Agricultural'</span><span class="p">,</span> <span class="s1">'18'</span><span class="p">:</span> <span class="s1">'Tram'</span><span class="p">,</span>\
    <span class="s1">'19'</span><span class="p">:</span> <span class="s1">'Van'</span><span class="p">,</span> <span class="s1">'20'</span><span class="p">:</span> <span class="s1">'Goods1'</span><span class="p">,</span> <span class="s1">'21'</span><span class="p">:</span> <span class="s1">'Goods2'</span><span class="p">,</span> <span class="s1">'22'</span><span class="p">:</span> <span class="s1">'Scooter'</span><span class="p">,</span> <span class="s1">'23'</span><span class="p">:</span> <span class="s1">'EMotorcycle'</span><span class="p">,</span> <span class="s1">'90'</span><span class="p">:</span> <span class="s1">'Other'</span><span class="p">,</span> <span class="s1">'97'</span><span class="p">:</span> <span class="s1">'Motorcycle5'</span><span class="p">,</span>\
    <span class="s1">'98'</span><span class="p">:</span> <span class="s1">'Goods3'</span><span class="p">,</span> <span class="s1">'99'</span><span class="p">:</span> <span class="s1">'Unknown'</span>
<span class="p">}</span>

<span class="c1"># df2[variable] = df2[variable].replace('0', pd.NA)</span>
<span class="n">df2</span> <span class="o">=</span> <span class="n">df2</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">ascending</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="n">_id</span><span class="p">])</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'viridis'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">statistics</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">barh</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'count'</span><span class="p">],</span> <span class="n">color</span><span class="o">=</span><span class="n">colors</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">'Number of Casualties'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">grid</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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/BNyT5oQQgghRCkkRZoQQgghRCkkRZoQQgghRCkkRZoQQgghRCkkRZoQQgghRCkkRZoQQgghRCkkRZoQQgghRCkkRZoQQgghRCkkRZoQokJJS0tDo9Fw8OBBa3dFdeLECdq2bYuDgwMtW7a0dnf+MR8fH5YsWVJom5iYmHJxrkKUJCnShBCPVEREBBqNhnnz5pks37RpExqNxkq9sq6ZM2fi5ORESkpKnombH3Tx4kVefvll6tati1arRafT0bNnz0K3KQ00Gg2bNm0yWTZx4sRS328hrE2KNCHEI+fg4MBbb73F9evXrd2VYnPv3j2Ltz1z5gzt27endu3auLu759smLS2NVq1a8e233/L2229z5MgRtm3bRpcuXRgzZozFx7YWZ2fnAs9VCHGfFGlCiEcuODgYT09P5s6dW2Cb/C6HLVmyBB8fH/VzREQEvXv3Zs6cOXh4eODq6srrr79OVlYWkyZNolq1ajz++OPExsbm2f+JEyd48skncXBwoGnTpuzevdtk/dGjR+nWrRvOzs54eHgwaNAgrly5oq7v3LkzUVFRjBs3jurVqxMaGprveeTk5PD666/z+OOPo9VqadmyJdu2bVPXazQafv31V15//XU0Gg0xMTH57mf06NFoNBr27dtH3759adCgAU2aNGH8+PH8/PPPartFixbRrFkznJyc0Ol0jB49mtu3b6vrz549S8+ePXFzc8PJyYkmTZqQkJAAQFxcHK6uribH/fsI55kzZ+jVqxceHh44OzvTunVrduzYkW+fAfXn1adPHzQajfo5v5/vBx98gJ+fHw4ODjRq1Ij33ntPXXfv3j2ioqLw8vLCwcGB2rVrF/rvR4jyQIo0IcQjZ2try5w5c3j33Xe5cOHCP9rXt99+y59//sn333/PokWLmDlzJs888wxubm7s3buXkSNHMmLEiDzHmTRpEhMmTOC3336jXbt29OzZk6tXrwJw48YNunbtir+/P7/88gvbtm3jr7/+Ijw83GQfa9euxd7enqSkJFauXJlv/9555x0WLlzIggULOHz4MKGhoTz77LOcOnUKgPT0dJo0acKECRNIT09n4sSJefZx7do1tm3bxpgxY3Bycsqz/sHCysbGhqVLl3Ls2DHWrl3Lt99+y+TJk9X1Y8aMwWAw8P3333PkyBHeeustnJ2dixY2/L927i8kqiWOA/hXy5dS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"/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=8a9423d0-de9e-4c65-9d24-427820564c51">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [44]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/casualty_type.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=f70123d0-a814-4a68-8531-edd73d08e6f9">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Casualty-Home-Area-Type-(casualty_home_area_type)">Casualty Home Area Type (casualty_home_area_type)<a class="anchor-link" href="#Casualty-Home-Area-Type-(casualty_home_area_type)">¶</a></h4><ul>
<li>Urban area (1)</li>
<li>Small town (2)</li>
<li>Rural (3)</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=46f5b911-26f8-4d3c-afa3-3cd4a0662505">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [45]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'casualty_severity'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'1'</span><span class="p">:</span> <span class="s1">'Urban area'</span><span class="p">,</span>
    <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'Small town'</span><span class="p">,</span>
    <span class="s1">'3'</span><span class="p">:</span> <span class="s1">'Rural'</span>
<span class="p">}</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="n">_id</span><span class="p">])</span>
<span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'proportion'</span><span class="p">]</span> <span class="o">*</span> <span class="mi">100</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'viridis'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mf">0.6</span><span class="p">,</span> <span class="mf">0.1</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">types</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="s1">'percentage'</span><span class="p">],</span> <span class="n">labels</span><span class="o">=</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">radius</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">center</span><span class="o">=</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span>
       <span class="n">wedgeprops</span><span class="o">=</span><span class="p">{</span><span class="s2">"linewidth"</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span> <span class="s2">"edgecolor"</span><span class="p">:</span> <span class="s2">"black"</span><span class="p">},</span> <span class="n">frame</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="n">centre_circle</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">Circle</span><span class="p">((</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span> <span class="mf">0.6</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">gca</span><span class="p">()</span><span class="o">.</span><span class="n">add_artist</span><span class="p">(</span><span class="n">centre_circle</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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"/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=8f7c7d13-6ced-458d-8eb8-b405c051208a">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [46]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/casualty_home_area_type.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=821942f2-ecca-4a0c-918c-89c866726a71">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h4 id="Casualty-IMD-Decile-(casualty_imd_decile)">Casualty IMD Decile (casualty_imd_decile)<a class="anchor-link" href="#Casualty-IMD-Decile-(casualty_imd_decile)">¶</a></h4><ul>
<li>1 to 10 from most deprived to least deprived.</li>
</ul>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=19afa687-8fa5-43bc-b5b3-3a171d5b6ddc">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [47]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>

<span class="n">variable</span> <span class="o">=</span> <span class="s1">'casualty_imd_decile'</span>
<span class="n">types</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">'1'</span><span class="p">:</span> <span class="s1">'most deprived   1'</span><span class="p">,</span>
    <span class="s1">'2'</span><span class="p">:</span> <span class="s1">'2'</span><span class="p">,</span>
    <span class="s1">'3'</span><span class="p">:</span> <span class="s1">'3'</span><span class="p">,</span>
    <span class="s1">'4'</span><span class="p">:</span> <span class="s1">'4'</span><span class="p">,</span>
    <span class="s1">'5'</span><span class="p">:</span> <span class="s1">'5'</span><span class="p">,</span>
    <span class="s1">'6'</span><span class="p">:</span> <span class="s1">'6'</span><span class="p">,</span>
    <span class="s1">'7'</span><span class="p">:</span> <span class="s1">'7'</span><span class="p">,</span>
    <span class="s1">'8'</span><span class="p">:</span> <span class="s1">'8'</span><span class="p">,</span>
    <span class="s1">'9'</span><span class="p">:</span> <span class="s1">'9'</span><span class="p">,</span>
    <span class="s1">'10'</span><span class="p">:</span> <span class="s1">'least deprived   10'</span>
<span class="p">}</span>

<span class="n">statistics</span> <span class="o">=</span> <span class="n">df2</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">(</span><span class="n">normalize</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">sort</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>
<span class="n">statistics</span> <span class="o">=</span> <span class="n">statistics</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="n">variable</span><span class="p">)</span>
<span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span> <span class="o">=</span> <span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">_id</span><span class="p">:</span> <span class="n">types</span><span class="p">[</span><span class="nb">str</span><span class="p">(</span><span class="n">_id</span><span class="p">)])</span>

<span class="n">fig</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">()</span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">get_cmap</span><span class="p">(</span><span class="s1">'viridis'</span><span class="p">)(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">statistics</span><span class="p">)))</span>
<span class="n">ax</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">statistics</span><span class="p">[</span><span class="n">variable</span><span class="p">],</span> <span class="n">statistics</span><span class="p">[</span><span class="s1">'count'</span><span class="p">],</span> <span class="n">color</span><span class="o">=</span><span class="n">colors</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xticks</span><span class="p">(</span><span class="n">rotation</span><span class="o">=</span><span class="mi">20</span><span class="p">,</span> <span class="n">ha</span><span class="o">=</span><span class="s1">'right'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">grid</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">"Casualty IMD Decile"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">"Number of Casualties"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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62rbPBtD00YTg4iIiN5vxXJEqnTp0qhfv77OtpIlS6JMmTLa7T4+PggICICdnR2srKzw5Zdfwt3dHS1b5k8peXp6om7duhg6dCjmzZuH5ORkTJkyBX5+ftoRpc8//xzLli3DhAkTMHLkSERFRWHLli3Yt29f4e4wERERGaViWUjpY+HChZDL5ejbty9ycnLg5eWFn3/+Wfu4iYkJ9u7di9GjR8Pd3R0lS5bE8OHDMXPm/84lcXZ2xr59+zBu3DgsXrwYlSpVwurVq+Hl5VUUu0RERERG5p0ppP7880+d+xYWFggODkZw8MtPnqxSpQrCwsJeGbd9+/Y4e/asFCkSERHRO6ZYniNFREREZAxYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZqFgWUnPmzEGzZs1QunRp2Nvbo1evXrhy5YpOm6dPn8LPzw9lypRBqVKl0LdvX6SkpOi0uXPnDrp16wZLS0vY29tj/PjxyMvL02nz559/onHjxjA3N0eNGjWwbt26t717REREVEwUy0Lqr7/+gp+fH44fP47IyEgolUp4enoiKytL22bcuHHYs2cPtm7dir/++gv37t1Dnz59tI+rVCp069YNubm5iImJwfr167Fu3TpMmzZN2+bmzZvo1q0bOnTogPj4eIwdOxaffvopDhw4UKj7S0RERMbJtKgTMER4eLjO/XXr1sHe3h5xcXFo164d0tPTsWbNGoSGhqJjx44AgF9//RV16tTB8ePH0bJlS0RERODSpUs4ePAgypcvj4YNG2LWrFmYOHEiZsyYATMzM6xYsQLOzs6YP38+AKBOnTo4evQoFi5cCC8vr0LfbyIiIjIuxbKQel56ejoAwM7ODgAQFxcHpVIJDw8PbZvatWujcuXKiI2NRcuWLREbGwtXV1eUL19e28bLywujR4/GxYsX0ahRI8TGxurE0LQZO3bsS3PJyclBTk6O9n5GRgYAQKlUQqlUit7XZ6nzzCWJk6cy17kVQ67nPgoS9CWozHRuxdD3tTFRi/+V0cSQIpa+eZsJJqL7MhPkOrdi6Ju3uQSD5poYUsTSO2+5THRfmhhSxNL7ODER35cmhhSx9M5bIf61Vfx/DIUEsfTNW2Eu/vdSYS7XuRVD77xLKET3pShhqnMrhtTvrW8aVyYIgvBWMigkarUaH330EdLS0nD06FEAQGhoKEaMGKFT0ABA8+bN0aFDBwQFBcHX1xe3b9/WmabLzs5GyZIlERYWhi5duqBmzZoYMWIEJk+erG0TFhaGbt26ITs7GyVKlCiQz4wZMxAYGFhge2hoKCwtLaXabSIiInqLsrOzMWjQIKSnp8PKyuql7Yr9iJSfnx8uXLigLaKK2uTJkxEQEKC9n5GRAScnJ3h6er7yhTCEOqWxJHHyVOY4GD8VHg1nwdQk5/VPeAV5+TN6tYu43VJUP0D+SJTq8iSY1J4LmUmuqFieVY7r1W7i+ZGi+gHyR6La3OuFo467oJLnvf4JrxDktlavdh0OzhTVD5A/EjVG2RiLFWeQK1OLinXYY9rrGwGov2GxqH6A/JGoWXbVMTX1OnIgLu8LQ8bo1a7JvGBR/QD5I1FT6lbF95duIUct7vNu3AQ/vdq1HSc+bzMTGb7uWBXzo24hVyUu7yML9cu768fijxOFQo7PhlbHyt+vQ6kUd5yEbdPvOOnbrOCH7jelMJdj2LdN8NvsOChzxOW9/dR0vdr1tBkuqh8gfyRq5Jq+WOuzHcon4v4O/pG2XnQ+L6KZUXqdYl1I+fv7Y+/evYiOjkalSpW02x0cHJCbm4u0tDTY2Nhot6ekpMDBwUHb5uTJkzrxNN/qe7bN89/0S0lJgZWV1QtHowDA3Nwc5uYFp60UCgUUCvHDoc9Sm4orep5napIDhciYcj33USayYNONlSs6nr6vjdjC5/lYYuPpm3euTCWqH91YatHx9M1bbOHzfCyx8fTOW2Th83wssfH0Pk5EFj7PxxIbT++8RRY+z1Iq1aLj6Zu3Mke630tljlp0PL3zfiLdVJrySZ7oeFK/t75p3GL5rT1BEODv74+dO3ciKioKzs7OOo83adIECoUChw4d0m67cuUK7ty5A3d3dwCAu7s7EhIS8ODBA22byMhIWFlZoW7duto2z8bQtNHEICIiovdbsRyR8vPzQ2hoKP744w+ULl0aycnJAABra2uUKFEC1tbW8PHxQUBAAOzs7GBlZYUvv/wS7u7uaNkyf0rJ09MTdevWxdChQzFv3jwkJydjypQp8PPz044off7551i2bBkmTJiAkSNHIioqClu2bMG+ffuKbN+JiIjIeBTLEanly5cjPT0d7du3R4UKFbT/Nm/erG2zcOFCdO/eHX379kW7du3g4OCAHTt2aB83MTHB3r17YWJiAnd3dwwZMgTDhg3DzJn/O5fE2dkZ+/btQ2RkJBo0aID58+dj9erVXPqAiIiIABTTESl9vmhoYWGB4OBgBAe//OTJKlWqICws7JVx2rdvj7Nnz75xjkRERPTuK5YjUkRERETGgIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIUUERERkYFYSBEREREZiIWUHoKDg1G1alVYWFigRYsWOHnyZFGnREREREaAhdRrbN68GQEBAZg+fTrOnDmDBg0awMvLCw8ePCjq1IiIiKiIsZB6jQULFmDUqFEYMWIE6tatixUrVsDS0hJr164t6tSIiIioiJkWdQLGLDc3F3FxcZg8ebJ2m1wuh4eHB2JjY1/4nJycHOTk5Gjvp6enAwBSU1OhVColzU/9SJqXL09liuzsbKSmmcLURCUqllzxn17tstLE5y6o5VBlZ8MkXQ6ZXFy8//7TL++8DLWofgBAUKuRnZ2NvAw1VHJx8fTNW56VJ6ofAJALamQrsyFXKiGXFU7epk9yRfUDAKaQIzs7G6ZPcqFCIeWdm/P6Rq+LIZfl552bA5VaEBVL7+NEJT5vuZCftzwvB/LCyhvijxP8/3EC5EJeSMcJTMX/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3LkDhUKBNWvWIC0tDcOHD9f2XaNGDdSoUQMAXnvQExHRu+NFRcvVq1cxb948bN26FeXLl4cgCJg8eTIGDRqEUqVKwdXVFUuXLsW+fftQqlQpqFQqlCpVCt9//z3atm0LJycnREVFwc/PD6ampnj8+DFKly79wv5dXV21eQAo8G1ver+90ZGgOXAePnyIZcuWwdLSEt27d0e7du0wf/58TJ48GdOnT8cff/wBc3NzLF26FDKZDHXr1kV6ejpOnjypjZOWlobSpUtrh0AfPnyIefPmwd/fH9bW1tiwYQPatGmj079m8IxFFBHRu0UzTaf5O//s1N3zRYtarcaaNWu0V784f/48Pv30U6xbt067oPKaNWvg4OCg/cZdWloali9fjm+//RY2Njbo3Lkzzpw5A29vb1SuXBlfffXVa79VxwKKXuSNpvaysrIwfPhwyGQylCpVCsOGDYNcLseQIUO037CrWLEiAGDixInYuXMnTp8+jeTkZIwePRoKhQIbN26Era0tdu/eDX9/f+zZswcNGjRAVlYW7t+/rx11IiKid19WVha+/fZb2NnZYfr06QUeT09Px5YtW+Dg4IBmzZrBwcEBarUaMTExqFq1KipVqoR79+5hwYIFWLVqFbp3744NGzboFDzZ2dmwtLRE7969kZOTg7CwMDx58gTh4eHYtWsXmjVrhs8//5wf0skgb1RalyxZEvb29ti1axcqV66MDh064IMPPsCMGTOQl5envZgjAIwePRrXrl3D0aNHUbNmTQQFBSE+Ph4eHh5o1qwZBg0ahKFDh6J27dra2JoiSnPxRyIiereVLFkS169fR3x8PO7cuQMgf1QqOzsbkydPhpOTE4KDgzFv3jy0bt0aFy5cgFwuR5s2bWBiYoIBAwagQYMGuHjxIrp06YKrV6/ixIkTAPIvNXbjxg2Ymppi3759ePjwIXr27AkAKFGiBHr37o3169fD398fpqamvEA9GeSNxyg//vhjODo6ahfMBIBevXohLy8PcXFx2qHYqlWrws3NDbt27UJmZqb2xPJx48ZhwIABuHLlCn744YcXXs/OxMSEw6dERO8Jb29v/P3339rTP2QyGc6cOYN9+/Zh7969iI+Px5EjR9CoUSMEBATg5s2bAPK/VZeSkoKIiAjs378f/v7+2g/wAHDkyBF89dVXqF27NoYOHYo2bdpg4MCBBfrXvG/x23ZkiDeuVtq0aYPq1avjxo0byMrKAgCUKVMGzZs3x19//YV//vlH23bgwIFYs2YNHjx4AABwdnbGkCFD8M0336BixYpQq9UceSIies95eXnB1NQUJ0+e1I4KrVq1CoMGDUK7du3w559/ws/PD7t374ZKpUJOTg5SUlJw4sQJuLm5aVcm1xRif/zxBzIyMtC6dWv07NkTq1evRmpqKubOnau9dMuzuFwOifHGhZSZmRlatWqFxMREJCQkaLcPGTIECQkJiI+P124bO3YsIiMjUa1aNZ0YmgUzeeIeERGVK1cOjRo1wvnz57XvK5mZmVi+fDlq166Nfv36ISMjA2FhYQgPD0ft2rVhb28PW1tbnDx5EocOHUJISAji4uIwdOhQtGjRAhkZGbCxscGoUaO0K5Pn5eVx+o4kZ1AV06NHD2RmZmqrfwD46KOPkJeXh3///Vc7ymRmZqY9gHU6/f8lFIiIiACge/fuePDgAU6fPg0A6NSpE+7du4dZs2bh+vXr+P333+Hh4QGVSoWzZ89CJpNh/PjxqFSpEgYPHowJEybA09MTP/74I+bPn69dUwr437IFXCyT3gaDvqLQokULlClTBhERERg4cCDKlSsHmUyGixcv6qzDwQOWiIj00alTJ/z00084efIkhgwZgpYtW0KhUCAtLQ0WFhYA8k9CX7duHa5cuYLy5cvD3d0d69evx7///osqVapoYz1/jVXOfNDbZPB3PTVfI7W0tNRuK126NFd7JSKiN2Zubo5WrVohOjoa8fHxaN68Ob777jtMmzYNmzZtQvPmzbFnzx5kZmZi3LhxsLOzA5D/rb+SJUsC+N9izTKZjB/kqdBIetFiIiIiQ504cQJ+fn4YOnQoxowZo10vKjw8HJcvX0bHjh3x6aefwszMrKhTJdISVUip1WpW/kREJBkvLy8oFAqsXbsW9vb2AKC9RquGSqXiubZkNEQt48opPCIikpLmtBHNdB2Qf76tIAhQq9UwMTHhcgVkVDi1R0RERGQgDikREZFR0aw1SFQccESKiIiIyEAckSIiIiIyEAspIiIiIgOxkCIiIiIyEAspIiIiIgOxkCIiIiIyEAspIiIiIgOxkCKid1LVqlWxaNGiok6j2Hr+5yeTybBr164iy4fIWLGQIqI3kpycjC+//BLVqlWDubk5nJyc0KNHDxw6dKioU3slqQqB9u3bY+zYsTr3ZTIZ5s6dW6Btt27dIJPJMGPGjALtZTIZzM3NUbFiRfTo0QM7dux4bd+ffPKJ9rkKhQLly5fHhx9+iLVr10KtVovet2edOnUKvr6+ksYkehexkCIivd26dQtNmjRBVFQUfvzxRyQkJCA8PBwdOnSAn59fUadXZJycnLBu3Tqdbf/88w8OHTqEChUqFGg/atQo3L9/H9evX8f27dtRt25deHt761W4dO7cGffv38etW7ewf/9+dOjQAWPGjEH37t2Rl5cn1S6hXLlysLS0lCwe0buKhRQR6e2LL76ATCbDyZMn0bdvX9SsWRP16tVDQEAAjh8/rm23YMECuLq6omTJknBycsIXX3yBzMxM7eO3b99Gjx49YGtri5IlS6JevXoICwsDAKxbtw42NjY6/e7atQsymUx7//r16+jZsyfKly+PUqVKoVmzZjh48OBL865atSqA/AviymQyVK1aFbdu3YJcLsfp06d12i5atAhVqlR5oxGe7t27499//8WxY8e029avXw9PT0/Y29sXaG9paQkHBwdUqlQJLVu2RFBQEFauXIlffvnllfsBAObm5nBwcEDFihXRuHFjfPvtt/jjjz+wf/9+nWIuLS0Nn376KcqVKwcrKyt07NgR586d04m1Z88eNGvWDBYWFihbtix69+6tfex1U6N3795F//79YWNjAzs7O/Ts2RO3bt169Q+K6B3EQoqI9JKamorw8HD4+fmhZMmSBR5/tviRy+VYsmQJLl68iPXr1yMqKgoTJkzQPu7n54ecnBxER0cjISEBQUFBKFWqlN65ZGZmomvXrjh06BDOnj2Lzp07o0ePHrhz584L2586dQoA8Ouvv+L+/fs4deoUqlatCg8PD/z66686bX/99Vd88sknkMv1//NoZmaGwYMH68Rat24dRo4cqXeM4cOHw9bWVq8pvud17NgRDRo00Hluv3798ODBA+zfvx9xcXFo3LgxOnXqhNTUVADAvn370Lt3b3Tt2hVnz57FoUOH0Lx5c736UyqV8PLyQunSpXHkyBEcO3YMpUqVQufOnZGbm/vG+RMVZyykiEgv165dgyAIqF279mvbjh07Fh06dEDVqlXRsWNHfP/999iyZYv28Tt37qB169ZwdXVFtWrV0L17d7Rr107vXBo0aIDPPvsM9evXh4uLC2bNmoXq1atj9+7dL2xf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"/>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=611fc959-07c4-4aeb-9e9c-0448956f8f1e">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [48]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># save the plot</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">'Plots/casualty_imd_decile.jpg'</span><span class="p">,</span> <span class="n">bbox_inches</span><span class="o">=</span><span class="s1">'tight'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
</main>
</body>
</html>
