---
title: "Практическое руководство. Перечисление присутствующих на компьютере часовых поясов"
description: "Практическое руководство. Перечисление присутствующих на компьютере часовых поясов"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c5ae4a6c-1790-4355-b5b1-879aaf956129
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 417a421f443f90e5f4ccd48bcabb3735dc5bc981

---

# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Практическое руководство. Перечисление присутствующих на компьютере часовых поясов

Для успешной работы с указанным часовым поясом необходимо, чтобы сведения об этом часовом поясе были доступны в системе. В операционных системах Windows, например, эти сведения хранятся в реестре. Тем не менее, хотя общее число часовых поясов, которые существуют по всему миру, велико, реестр содержит сведения только о подмножестве из них. Кроме того, реестр сам является динамической структурой, содержимое которой подвержено преднамеренным и случайным изменениям. В итоге приложение не может всегда предполагать, что конкретный часовой пояс определен и доступен в системе. Первым шагом для многих приложений, использующих данные о часовых поясах, является определение доступности требуемого часового пояса на локальном компьютере или предоставление пользователю списка часовых поясов для выбора. Для этого необходимо, чтобы приложение перечислило часовые пояса, определенные в локальной системе. 

## <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Перечисление часовых поясов, присутствующих в локальной системе

1. Вызовите метод [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones). Этот метод возвращает универсальную коллекцию [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) объектов [TimeZoneInfo](xref:System.TimeZoneInfo). Элементы коллекции сортируются по свойству [DisplayName](xref:System.TimeZoneInfo.DisplayName). Пример:

    ```csharp
    ReadOnlyCollection<TimeZoneInfo> tzCollection;
    tzCollection = TimeZoneInfo.GetSystemTimeZones();
    ```

    ```vb
    Dim tzCollection As ReadOnlyCollection(Of TimeZoneInfo) = TimeZoneInfo.GetSystemTimeZones
    ```

2. Перечислите отдельные объекты [TimeZoneInfo](xref:System.TimeZoneInfo) в коллекции с помощью цикла `foreach` (в C#) или цикла `For Each…Next` (в Visual Basic) и выполните все необходимые действия с каждым объектом. Например, следующий код перечисляет коллекцию [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) объектов [TimeZoneInfo](xref:System.TimeZoneInfo), возвращенную на шаге 1, и выводит на консоль список отображаемых имен всех часовых поясов.

    ```csharp
    foreach (TimeZoneInfo timeZone in tzCollection)
    Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName);
    ```

    ```vb
    For Each timeZone As TimeZoneInfo In tzCollection
        Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName)
    Next
    ```

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](index.md)

[Поиск часового пояса, заданного в локальной системе](finding-the-time-zones-on-local-system.md)




<!--HONumber=Nov16_HO1-->


