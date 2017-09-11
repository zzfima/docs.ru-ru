---
title: "Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени"
description: "Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d6858a5c-02ab-4367-9e08-fa22c051c38d
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ede8d021a4f524cf37f7ad00b6aed89d1b1729f8
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="5f182-104">Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="5f182-104">How to: let users resolve ambiguous times</span></span>

<span data-ttu-id="5f182-105">Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="5f182-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="5f182-106">Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время.</span><span class="sxs-lookup"><span data-stu-id="5f182-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="5f182-107">При обработке неоднозначного времени можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="5f182-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="5f182-108">Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="5f182-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="5f182-109">Сделать предположение о том, насколько время соответствует времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="5f182-109">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="5f182-110">Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="5f182-110">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="5f182-111">В этом разделе показано, как предоставить пользователям возможность разрешать неоднозначность времени.</span><span class="sxs-lookup"><span data-stu-id="5f182-111">This article shows how to let a user resolve an ambiguous time.</span></span>

## <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="5f182-112">Предоставление пользователю возможности разрешать неоднозначность времени</span><span class="sxs-lookup"><span data-stu-id="5f182-112">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="5f182-113">Получите значение даты и времени, введенное пользователем.</span><span class="sxs-lookup"><span data-stu-id="5f182-113">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="5f182-114">Вызовите метод [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) или [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)), чтобы определить, является ли время неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="5f182-114">Call the [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="5f182-115">Предоставьте пользователю возможность выбрать нужное смещение.</span><span class="sxs-lookup"><span data-stu-id="5f182-115">Let the user select the desired offset.</span></span>

4. <span data-ttu-id="5f182-116">Получите дату и время в формате UTC путем вычитания выбранного пользователем смещения из локального времени.</span><span class="sxs-lookup"><span data-stu-id="5f182-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

5. <span data-ttu-id="5f182-117">Вызовите метод `static` (`Shared` в Visual Basic ) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)), чтобы задать значение даты и времени в формате UTC для свойства [Kind](xref:System.DateTime.Kind) равным [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span><span class="sxs-lookup"><span data-stu-id="5f182-117">Call the `static` (`Shared` in Visual Basic ) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="5f182-118">Пример</span><span class="sxs-lookup"><span data-stu-id="5f182-118">Example</span></span>

<span data-ttu-id="5f182-119">В следующем примере пользователю предлагается ввести значение даты и времени и, если оно неоднозначно, выбрать время в формате UTC, которому сопоставлено неоднозначное время.</span><span class="sxs-lookup"><span data-stu-id="5f182-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span> <span data-ttu-id="5f182-120">В примере используется объект [DateTime](xref:System.DateTime), который при желании можно заменить на объект [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="5f182-120">The example uses a [DateTime](xref:System.DateTime) object; you can substitute a [DateTimeOffset](xref:System.DateTimeOffset) object if desired.</span></span>

```csharp
private void GetUserDateInput()
{
   // Get date and time from user
   DateTime inputDate = GetUserDateTime();
   DateTime utcDate;

   // Exit if date has no significant value
   if (inputDate == DateTime.MinValue) return;

   if (TimeZoneInfo.Local.IsAmbiguousTime(inputDate))
   {
      Console.WriteLine("The date you've entered is ambiguous.");
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:");
      TimeSpan[] offsets = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate);
      for (int ctr = 0; ctr < offsets.Length; ctr++)
      {
         Console.WriteLine("{0}.) {1} hours, {2} minutes", ctr, offsets[ctr].Hours, offsets[ctr].Minutes);
      }
      Console.Write("> ");
      int selection = Convert.ToInt32(Console.ReadLine());

      // Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = DateTime.SpecifyKind(inputDate - offsets[selection], DateTimeKind.Utc);

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());
   }
   else
   {
      utcDate = inputDate.ToUniversalTime();
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());    
   }
}

private DateTime GetUserDateTime() 
{
   bool exitFlag = false;             // flag to exit loop if date is valid
   string dateString;  
   DateTime inputDate = DateTime.MinValue;

   Console.Write("Enter a local date and time: ");
   while (! exitFlag)
   {
      dateString = Console.ReadLine();
      if (dateString.ToUpper() == "E")
         exitFlag = true;

      if (DateTime.TryParse(dateString, out inputDate))
         exitFlag = true;
      else
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ");
   }

   return inputDate;        
}
```

```vb
Private Sub GetUserDateInput()
   ' Get date and time from user
   Dim inputDate As Date = GetUserDateTime()
   Dim utcDate As Date

   ' Exit if date has no significant value
   If inputDate = Date.MinValue Then Exit Sub

   If TimeZoneInfo.Local.IsAmbiguousTime(inputDate) Then
      Console.WriteLine("The date you've entered is ambiguous.")
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:")
      Dim offsets() As TimeSpan = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate)
      For ctr As Integer = 0 to offsets.Length - 1
         Dim zoneDescription As String
         If offsets(ctr).Equals(TimeZoneInfo.Local.BaseUtcOffset) Then 
            zoneDescription = TimeZoneInfo.Local.StandardName
         Else
            zoneDescription = TimeZoneInfo.Local.DaylightName
         End If
         Console.WriteLine("{0}.) {1} hours, {2} minutes ({3})", _
                           ctr, offsets(ctr).Hours, offsets(ctr).Minutes, zoneDescription)
      Next         
      Console.Write("> ")
      Dim selection As Integer = CInt(Console.ReadLine())

      ' Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = Date.SpecifyKind(inputDate - offsets(selection), DateTimeKind.Utc)

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())
   Else
      utcDate = inputDate.ToUniversalTime()
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())    
   End If
End Sub

Private Function GetUserDateTime() As Date
   Dim exitFlag As Boolean = False            ' flag to exit loop if date is valid
   Dim dateString As String 
   Dim inputDate As Date = Date.MinValue

   Console.Write("Enter a local date and time: ")
   Do While Not exitFlag
      dateString = Console.ReadLine()
      If dateString.ToUpper = "E" Then exitFlag = True
      If Date.TryParse(dateString, inputDate) Then
         exitFlag = true
      Else   
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ")
      End If
   Loop

   Return inputDate        
End Function
```

<span data-ttu-id="5f182-121">В главной части примера используется массив объектов [TimeSpan](xref:System.TimeSpan) для указания возможных смещений неоднозначного времени относительно времени UTC.</span><span class="sxs-lookup"><span data-stu-id="5f182-121">The core of the example code uses an array of [TimeSpan](xref:System.TimeSpan) objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="5f182-122">Однако эти смещения скорее всего не будут иметь значения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5f182-122">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="5f182-123">Для уточнения значений этих смещений в коде также учитывается, представляет ли смещение стандартное время местного часового пояса или его летнее время.</span><span class="sxs-lookup"><span data-stu-id="5f182-123">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="5f182-124">Код определяет, какое время является стандартным, а какое летним, сравнивая смещение со значением свойства [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset).</span><span class="sxs-lookup"><span data-stu-id="5f182-124">The code determines which time is standard and which time is daylight by comparing the offset with the value of the [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span> <span data-ttu-id="5f182-125">Это свойство указывает разницу между временем UTC и стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="5f182-125">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="5f182-126">В этом примере все ссылки на местный часовой пояс выполняются через свойство [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local). Местный часовой пояс никогда не назначается в качестве переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="5f182-126">In this example, all references to the local time zone are made through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="5f182-127">Это рекомендуется, поскольку вызов другого метода приведет к сбросу кэшированных данных и внесет изменения во все объекты, которым назначен этот часовой пояс, после чего они станут недействительны.</span><span class="sxs-lookup"><span data-stu-id="5f182-127">This is a recommended practice because another call could clear the cached data and invalidate any objects that the local time zone is assigned to.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f182-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5f182-128">See Also</span></span>

[<span data-ttu-id="5f182-129">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="5f182-129">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="5f182-130">Практическое руководство. Разрешение проблемы неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="5f182-130">How to: resolve ambiguous times</span></span>](resolve-ambiguous-times.md)


