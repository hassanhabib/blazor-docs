---
title: "ListView how to trace events of listview"
component: "ListView"
description: "Blazor ListView how to section, get selected item, dual list, listview filtering, add & remove items from listview, grid layout using listview, listview drag & drop."
---

# How to trace events of ListView

The ListView control triggers events based on its actions. The events can be used as extension points to perform
custom operations. Refer to the following steps to trace the ListView events:

1. Render the ListView with `DataSource`, and bind the `OnActionBegin`, `OnActionComplete`,
and `Selected` events.

2. Perform custom operations in `OnActionBegin`, `OnActionComplete`, and `Selected` events.

3. Provide event log details for `OnActionBegin` and `OnActionComplete` events, and they will be displayed in the event trace panel
when the ListView action starts and the dataSource bound successfully.

4. Get the selected item details from the `SelectEventArgs` in the
select event, and display the selected list item text in the event trace panel while selecting list items.

5. Use clear button to remove event trace information.

```C#
@using Syncfusion.Blazor.Lists

<div id="container">
    <div class="flex vertical-center">
        <div class="sample padding">
            <SfListView DataSource="@DataSource">
                <ListViewFieldSettings Id="Id" Text="Text"></ListViewFieldSettings>
                <ListViewEvents TValue="ListDataModel"
                                Selected="@(e => Events.Add(e.Text +" is selected"))"
                                OnActionBegin="@(e => Events.Add("OnActionBegin is triggered"))"
                                OnActionComplete="@(e => Events.Add("OnActionComplete is triggered"))">
                </ListViewEvents>
            </SfListView>
        </div>
        <div class="sample padding tracker">
            <ul style="list-style: none">
                @for(var i = Events.Count -1; i >= 0; i--)
                {
                    <li>@Events[i]</li>
                }
            </ul>
        </div>
    </div>
</div>

@code
{
    List<string> Events = new List<string>();

    List<ListDataModel> DataSource = new List<ListDataModel>() {
        new ListDataModel { Id = "1", Text = "Text 1" },
        new ListDataModel { Id = "2", Text = "Text 2" },
        new ListDataModel { Id = "3", Text = "Text 3" },
        new ListDataModel { Id = "4", Text = "Text 4" },
        new ListDataModel { Id = "5", Text = "Text 5" },
        new ListDataModel { Id = "6", Text = "Text 6" },
        new ListDataModel { Id = "7", Text = "Text 7" },
    };

    class ListDataModel
    {
        public string Id
        {
            get;
            set;
        }
        public string Text
        {
            get;
            set;
        }
    }
}
<style>
    #container .e-listview {
        box-shadow: 0 1px 4px #ddd;
        border-bottom: 1px solid #ddd;
    }

    .tracker {
        max-height: 250px;
        overflow: auto;
    }

    .sample {
        justify-content: center;
        min-height: 280px;
        width: 350px;
    }

    .vertical-center {
        align-items: center;
    }

    .padding {
        padding: 4px;
    }

    .flex {
        display: flex;
    }

    .flex__center {
        justify-content: center;
    }

    .margin {
        margin: 10px;
    }
</style>
```

![ListView - Events](../images/list/trace-events-of-listview.png)
