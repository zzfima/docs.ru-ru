---
title: "Практическое руководство. Перечисление присутствующих на компьютере часовых поясов | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "перечисление часовых поясов [платформа .NET Framework]"
  - "часовые пояса [платформа .NET Framework], перечисление"
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Перечисление присутствующих на компьютере часовых поясов
Для успешной работы с указанным часовым поясом необходимо, чтобы сведения об этом часовом поясе были доступны в системе.  В операционных системах Windows XP и Windows Vista эти сведения хранятся в реестре.  Тем не менее, хотя общее число часовых поясов, которые существуют по всему миру, велико, реестр содержит сведения только о подмножестве из них.  Кроме того, реестр сам является динамической структурой, содержимое которой подвержено преднамеренным и случайным изменениям.  В итоге приложение не может всегда предполагать, что определенный часовой пояс определен и доступен в системе.  Первым шагом для многих приложений, использующих данные о часовых поясах, является определение доступности требуемого часового пояса на локальном компьютере или предоставление пользователю списка часовых поясов для выбора.  Для этого необходимо, чтобы приложение перечислило часовые пояса, определенные в локальной системе.  
  
> [!NOTE]
>  Если приложение полагается на наличие определенного часового пояса, который может быть не определен в локальной системе, то приложение может проверить его наличие, сериализовав и десериализовав данные о часовом поясе.  Затем часовой пояс может быть добавлен в элемент управления "список" и выбран пользователем.  Дополнительные сведения см. в разделах [Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) и [Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
  
### Перечисление часовых поясов, присутствующих в локальной системе  
  
1.  Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=fullName>.  Этот метод возвращает универсальную коллекцию <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> объектов <xref:System.TimeZoneInfo>.  Элементы коллекции сортируются по свойству <xref:System.TimeZoneInfo.DisplayName%2A>.  Примеры.  
  
     [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
     [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]  
  
2.  Перечислите отдельные объекты <xref:System.TimeZoneInfo> в коллекции с помощью цикла `foreach` \(в C\#\) или цикла `For Each`…`Next` \(в Visual Basic\) и выполните все необходимые действия с каждым объектом.  Например, следующий код перечисляет коллекцию <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> объектов <xref:System.TimeZoneInfo>, возвращенную на шаге 1, и выводит на консоль список отображаемых имен всех часовых поясов.  
  
     [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
     [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]  
  
### Предоставление пользователю списка часовых поясов, присутствующих в локальной системе  
  
1.  Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=fullName>.  Этот метод возвращает универсальную коллекцию <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> объектов <xref:System.TimeZoneInfo>.  
  
2.  Присвойте коллекцию, возвращенную на шаге 1, свойству `DataSource` элемента управления "список" Windows Forms или ASP.NET.  
  
3.  Получите выбранный пользователем объект <xref:System.TimeZoneInfo>.  
  
 Пример показывает это на основе приложения Windows.  
  
## Пример  
 В примере запускается приложение Windows, которое отображает в списке часовые пояса, определенные в системе.  Затем выводится диалоговое окно, содержащее значение свойства <xref:System.TimeZoneInfo.DisplayName%2A> объекта часового пояса, выбранного пользователем.  
  
 [!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
 [!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]  
  
 Большинство элементов управления "список" \(таких как элементы управления <xref:System.Windows.Forms.ListBox?displayProperty=fullName> или <xref:System.Web.UI.WebControls.BulletedList?displayProperty=fullName>\) позволяют присвоить коллекцию объектов их свойству `DataSource`, если коллекция реализует интерфейс <xref:System.Collections.IEnumerable>. \(Это реализуется с помощью универсального класса <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.\) Чтобы отобразить отдельный объект коллекции, элемент управления вызывает метод объекта `ToString` для извлечения строки, которая используется для представления объекта.  Для объектов <xref:System.TimeZoneInfo> метод `ToString` возвращает отображаемое имя объекта <xref:System.TimeZoneInfo> \(значение его свойства <xref:System.TimeZoneInfo.DisplayName%2A>\).  
  
> [!NOTE]
>  Поскольку элемент управления "список" вызывает метод объекта `ToString`, то можно присвоить коллекцию объектов <xref:System.TimeZoneInfo> элементу управления, отображать понятное имя каждого объекта и получать выбранный пользователем объект <xref:System.TimeZoneInfo>.  Это избавляет от необходимости извлекать строку для каждого объекта в коллекции, присваивать этой строке коллекции, которая, в свою очередь, присваивается свойству `DataSource` элемента управления, получать строку, которую выбрал пользователь, и затем использовать данную строку для получения объекта, который она описывает.  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Чтобы ссылка на System.Core.dll была добавлена в проект.  
  
-   Чтобы был осуществлен импорт следующих пространств имен:  
  
     <xref:System> \(в коде C\#\)  
  
     <xref:System.Collections.ObjectModel>  
  
## См. также  
 [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)   
 [Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)   
 [Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)