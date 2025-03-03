---
title: "@univerjs/sheets"
---

[![npm version](https://img.shields.io/npm/v/@univerjs/sheets)](https://npmjs.org/package/@univerjs/sheets)

@univerjs/sheet serves as the foundation for the core business logic of spreadsheets, with base-sheets designed to be UI-agnostic, allowing for functionality such as collaborative editing to be implemented in a Node.js environment.

@univerjs/sheets provides the following capabilities for Univer Sheet:

* Core functionality, including numerical formatting, selection management, permissions, etc.
* Commands/mutations for modifying spreadsheet data
* Formula core functionality
* Core numerical formatting functionality

## `SheetInterceptorService`

`SheetInterceptorService` is a more specialized service provided by @univerjs/sheets that allows higher-level business to modify the results of operations such as obtaining cell data, retrieving row/column hiding information from a Worksheet, and supplementing mutations or operations at specific command executions. This service's primary goal is to enable specific functionalities, including:

1. Sheet formulas
2. Sheet conditional formatting
3. Sheet data validation
4. Sheet pivot tables

For detailed usage, please refer to the API documentation.

### When to use `SheetInterceptorService` and when not to?

Use `SheetInterceptorService` when multiple features need to operate on the same data or state, but do not have a clear dependency relationship. For example: pivot tables, formulas, conditional formatting, data validation, and raw cell data can all affect how other features retrieve a cell's value, but they do not depend on each other. In this case, using `SheetInterceptorService` to implement these features is appropriate.

However, if one feature relies explicitly on another feature, such as a formula needing to perform certain actions when the fill down or copy-paste functions are called, the formula module should directly depend on the fill down and copy-paste modules, instead of using `SheetInterceptorService` for implementation.

<!--package-locales start-->
<!--package-locales end-->

<!--package-assets start-->
<!--package-assets end-->