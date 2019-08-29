---
title: Практическое руководство. Перечисление присутствующих на компьютере часовых поясов
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afc3b57659dd6719f72cefba8a6d2f1abe08c0d0
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106655"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Практическое руководство. Перечисление присутствующих на компьютере часовых поясов

Для успешной работы с указанным часовым поясом необходимо, чтобы сведения об этом часовом поясе были доступны в системе. В операционных системах Windows XP и Windows Vista эти сведения хранятся в реестре. Тем не менее, хотя общее число часовых поясов, которые существуют по всему миру, велико, реестр содержит сведения только о подмножестве из них. Кроме того, реестр сам является динамической структурой, содержимое которой подвержено преднамеренным и случайным изменениям. В итоге приложение не может всегда предполагать, что конкретный часовой пояс определен и доступен в системе. Первым шагом для многих приложений, использующих данные о часовых поясах, является определение доступности требуемого часового пояса на локальном компьютере или предоставление пользователю списка часовых поясов для выбора. Для этого необходимо, чтобы приложение перечислило часовые пояса, определенные в локальной системе.

> [!NOTE]
> Если приложение полагается на присутствие определенного часового пояса, которое не может быть определено в локальной системе, приложение может обеспечить его присутствие путем сериализации и десериализации сведений о часовом поясе. Затем часовой пояс можно добавить в элемент управления "список", чтобы пользователь приложения мог выбрать его. Подробную информацию см. в разделе [Практическое руководство. Сохраняйте Часовые пояса во внедренном](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) ресурсе и [последующее: Восстановление часовых поясов из внедренного](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)ресурса.

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Перечисление часовых поясов, присутствующих в локальной системе

1. Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. Метод возвращает универсальную <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> <xref:System.TimeZoneInfo> коллекцию объектов. Записи в коллекции сортируются по их <xref:System.TimeZoneInfo.DisplayName%2A> свойству. Например:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Перечисляет отдельные <xref:System.TimeZoneInfo> объекты в коллекции с `foreach` помощью цикла C# `For Each`(в) или...`Next` цикл (в Visual Basic) и выполните необходимую обработку для каждого объекта. Например, следующий код перечисляет <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> <xref:System.TimeZoneInfo> коллекцию объектов, возвращенных на шаге 1, и отображает отображаемое имя каждого часового пояса в консоли.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Предоставление пользователю списка часовых поясов, имеющихся в локальной системе

1. Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. Метод возвращает универсальную <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> <xref:System.TimeZoneInfo> коллекцию объектов.

2. Назначьте коллекцию, возвращенную в шаге 1 `DataSource` , свойству элемента управления Windows Forms или ASP.NET List.

3. <xref:System.TimeZoneInfo> Получение объекта, выбранного пользователем.

В примере показана Иллюстрация для приложения Windows.

## <a name="example"></a>Пример

В примере запускается приложение Windows, которое отображает Часовые пояса, определенные в системе, в поле со списком. Затем в примере отображается диалоговое окно, содержащее значение <xref:System.TimeZoneInfo.DisplayName%2A> свойства объекта часового пояса, выбранного пользователем.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Большинство элементов управления "список" ( <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> например <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> , или) позволяют назначить коллекцию переменных объекта их `DataSource` <xref:System.Collections.IEnumerable> свойству, если эта коллекция реализует интерфейс. (Это делается <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> универсальным классом.) Чтобы отобразить отдельный объект в коллекции, элемент управления вызывает `ToString` метод объекта для извлечения строки, используемой для представления объекта. В случае <xref:System.TimeZoneInfo> с объектами `ToString` метод возвращает <xref:System.TimeZoneInfo> отображаемое имя объекта (значение его <xref:System.TimeZoneInfo.DisplayName%2A> свойства).

> [!NOTE]
> Поскольку элементы управления "список" вызывают `ToString` метод объекта, можно присвоить элементу управления <xref:System.TimeZoneInfo> коллекцию объектов, отображать для каждого <xref:System.TimeZoneInfo> объекта понятное имя и получать объект, выбранный пользователем. Это избавляет от необходимости извлекать строку для каждого объекта в коллекции, присваивать строку коллекции, которая, в свою очередь, присвоена `DataSource` свойству элемента управления, получать строку, выбранную пользователем, а затем использовать эту строку для извлечения объекта. его описание. 

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- Для импорта следующих пространств имен:

  <xref:System>(в C# коде)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
