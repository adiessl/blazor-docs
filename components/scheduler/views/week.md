---
title: Week
page_title: Scheduler - Week View
description: Week View in the Scheduler for Blazor.
slug: scheduler-views-week
tags: telerik,blazor,scheduler,view,week
published: True
position: 3
---

# Week View

The Week view of the scheduler shows the entire week to the user.

The `Date` parameter of the scheduler controls which week is displayed. The first day depends on the current culture's `FirstDayOfWeek`.

In this article:

* [Example](#example)
* [View Parameters](#view-parameters)
	* [Slots](#slots)
* [Resource Grouping](#resource-grouping-in-the-week-view)

>caption Figure: Week View in the scheduler

![](images/week-view-sample.png)

## Example

>caption Declare the Week View in the markup

>tip You can declare other views as well, this example adds only the week view for brevity.

````CSHTML
@* Define the day view. The screenshot above is the result from this code snippet *@

<TelerikScheduler Data="@Appointments" @bind-Date="@StartDate" Height="600px" Width="800px">
    <SchedulerViews>
        <SchedulerWeekView StartTime="@DayStart" EndTime="@DayEnd" WorkDayStart="@WorkDayStart" WorkDayEnd="@WorkDayEnd" />
    </SchedulerViews>
</TelerikScheduler>

@code {
    public DateTime StartDate { get; set; } = new DateTime(2019, 12, 2);
    //the time portions are important
    public DateTime DayStart { get; set; } = new DateTime(2000, 1, 1, 8, 0, 0);
    public DateTime DayEnd { get; set; } = new DateTime(2000, 1, 1, 20, 0, 0);
    public DateTime WorkDayStart { get; set; } = new DateTime(2000, 1, 1, 9, 0, 0);
    public DateTime WorkDayEnd { get; set; } = new DateTime(2000, 1, 1, 17, 0, 0);
    List<SchedulerAppointment> Appointments = new List<SchedulerAppointment>()
    {
            new SchedulerAppointment
            {
                Title = "Board meeting",
                Description = "Q4 is coming to a close, review the details.",
                Start = new DateTime(2019, 12, 5, 10, 00, 0),
                End = new DateTime(2019, 12, 5, 11, 30, 0)
            },

            new SchedulerAppointment
            {
                Title = "Vet visit",
                Description = "The cat needs vaccinations and her teeth checked.",
                Start = new DateTime(2019, 12, 2, 11, 30, 0),
                End = new DateTime(2019, 12, 2, 12, 0, 0)
            },

            new SchedulerAppointment
            {
                Title = "Planning meeting",
                Description = "Kick off the new project.",
                Start = new DateTime(2019, 12, 6, 9, 30, 0),
                End = new DateTime(2019, 12, 6, 12, 45, 0)
            },

            new SchedulerAppointment
            {
                Title = "Trip to Hawaii",
                Description = "An unforgettable holiday!",
                IsAllDay = true,
                Start = new DateTime(2019, 11, 27),
                End = new DateTime(2019, 12, 05)
            }
    };

    public class SchedulerAppointment
    {
        public string Title { get; set; }
        public string Description { get; set; }
        public DateTime Start { get; set; }
        public DateTime End { get; set; }
        public bool IsAllDay { get; set; }
    }
}
````


@[template](/_contentTemplates/scheduler/views.md#day-views-common-properties)

@[template](/_contentTemplates/scheduler/views.md#visible-times-tip)

@[template](/_contentTemplates/scheduler/views.md#day-slots-explanation)

## Resource Grouping in the Week View

You can configure the Week view to display events that are [grouped by a resource]({%slug scheduler-resource-grouping%}).

>caption The result from the code snippet below.

![](images/scheduler-resource-grouping-week-view.png)

>caption Resource Grouping in a Week view.

@[template](/_contentTemplates/scheduler/views.md#resource-grouping-code-snippet-for-examples)

## See Also

  * [Views]({%slug scheduler-views-overview%})
  * [Navigation]({%slug scheduler-navigation%})
  * [Live Demo: Scheduler Week View](https://demos.telerik.com/blazor-ui/scheduler/week-view)
  
