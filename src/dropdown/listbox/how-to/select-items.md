---
title: "Select items to the listbox"
component: "ListBox"
description: "ListBox component supports select of items to the listbox."
---

# Select items to the listbox

In the following example, `Bugatti Chiron` is selected using [`SelectItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.SfListBox%601~SelectItems.html) method.

```csharp
@using Syncfusion.Blazor.DropDowns

<SfListBox TValue="string[]" TItem="VehicleData" DataSource="@Vehicles" @ref="ListBoxObj">
    <ListBoxEvents TValue="string[]" Created="created"></ListBoxEvents>
    <ListBoxFieldSettings Text="Text" Value="Id" />
</SfListBox>

@code {
    SfListBox<string[]> ListBoxObj;
    public List<VehicleData> Vehicles = new List<VehicleData> {
        new VehicleData { Text = "Hennessey Venom", Id = "Vehicle-01" },
        new VehicleData { Text = "Bugatti Chiron", Id = "Vehicle-02" },
        new VehicleData { Text = "Bugatti Veyron Super Sport", Id = "Vehicle-03" },
        new VehicleData { Text = "SSC Ultimate Aero", Id = "Vehicle-04" },
        new VehicleData { Text = "Koenigsegg CCR", Id = "Vehicle-05" },
        new VehicleData { Text = "McLaren F1", Id = "Vehicle-06" },
        new VehicleData { Text = "Aston Martin One- 77", Id = "Vehicle-07" },
        new VehicleData { Text = "Jaguar XJ220", Id = "Vehicle-08" }
    };

    public class VehicleData {
      public string Text  { get; set; }
      public string Id  { get; set; }
    }
    public string[] Value = new string[] { "Bugatti Chiron" };
    private void created(object args)
    {
        ListBoxObj.SelectItems(this.Value, true);
    }
}

```

Output will be shown as

![ListBox](./../images/select.png)