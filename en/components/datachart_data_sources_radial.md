---
title: Data Chart Component - Native Angular | Ignite UI for Angular
_description: The Ignite UI for Angular Data Chart component is TODO.
_keywords: Ignite UI for Angular, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components, Native Angular Components Library, Angular Chart, Angular Data Chart Control, Angular Data Chart Example, Angular Data Chart Component, Angular Data Chart
---

## Sample Data Source for Radial Series

This topic provides an example on how to implement data source for [Radial Series](datachart_series_types_radial.md)

```typescript
export class SampleRadialData {

    public static create(): any[] {
        const data: any[] = [];
        data.push( { "Spending": 20, "Budget": 60, "Department": "Admin" });
        data.push( { "Spending": 80, "Budget": 40, "Department": "Sales" });
        data.push( { "Spending": 30, "Budget": 60, "Department": "IT" });
        data.push( { "Spending": 80, "Budget": 40, "Department": "Marketing" });
        data.push( { "Spending": 40, "Budget": 60, "Department": "Research" });
        data.push( { "Spending": 60, "Budget": 20, "Department": "Support" });
        return data;
    }
}
```
