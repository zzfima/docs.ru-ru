---
title: Руководство. Перечисление имеющихся на компьютере часовых поясов
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
ms.openlocfilehash: aa8962c8aea208778983610041937dc3f75c1f1e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159446"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Руководство. Перечисление имеющихся на компьютере часовых поясов

Для успешной работы с указанным часовым поясом необходимо, чтобы сведения об этом часовом поясе были доступны в системе. В операционных системах Windows XP и Windows Vista эти сведения хранятся в реестре. Тем не менее, хотя общее число часовых поясов, которые существуют по всему миру, велико, реестр содержит сведения только о подмножестве из них. Кроме того, реестр сам является динамической структурой, содержимое которой подвержено преднамеренным и случайным изменениям. В итоге приложение не может всегда предполагать, что конкретный часовой пояс определен и доступен в системе. Первым шагом для многих приложений, использующих данные о часовых поясах, является определение доступности требуемого часового пояса на локальном компьютере или предоставление пользователю списка часовых поясов для выбора. Для этого необходимо, чтобы приложение перечислило часовые пояса, определенные в локальной системе.

> [!NOTE]
> Если приложение полагается на присутствие определенного часового пояса, которое не может быть определено в локальной системе, приложение может обеспечить его присутствие путем сериализации и десериализации сведений о часовом поясе. Затем часовой пояс можно добавить в элемент управления "список", чтобы пользователь приложения мог выбрать его. Дополнительные сведения см. [в разделе как сохранить Часовые пояса во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) и [как восстановить Часовые пояса из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Перечисление часовых поясов, присутствующих в локальной системе

1. Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> . Метод возвращает универсальную коллекцию <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> объектов <xref:System.TimeZoneInfo>. Записи в коллекции сортируются по свойству <xref:System.TimeZoneInfo.DisplayName%2A>. Пример:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Перечисление отдельных объектов <xref:System.TimeZoneInfo> в коллекции с помощью цикла `foreach` (в C#) или `For Each`...`Next` цикл (в Visual Basic) и выполните необходимую обработку для каждого объекта. Например, следующий код перечисляет <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию объектов <xref:System.TimeZoneInfo>, возвращаемых на шаге 1, и отображает отображаемое имя каждого часового пояса в консоли.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Предоставление пользователю списка часовых поясов, имеющихся в локальной системе

1. Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> . Метод возвращает универсальную коллекцию <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> объектов <xref:System.TimeZoneInfo>.

2. Назначьте коллекцию, возвращенную в шаге 1, свойству `DataSource` элемента управления списка Windows Forms или ASP.NET.

3. Получение объекта <xref:System.TimeZoneInfo>, выбранного пользователем.

В примере показана Иллюстрация для приложения Windows.

## <a name="example"></a>Пример

В примере запускается приложение Windows, которое отображает Часовые пояса, определенные в системе, в поле со списком. Затем в примере отображается диалоговое окно, содержащее значение свойства <xref:System.TimeZoneInfo.DisplayName%2A> объекта часового пояса, выбранного пользователем.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Большинство элементов управления "список" (например, <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> или <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType>) позволяют присвоить коллекции объектных переменных свойству `DataSource`, если эта коллекция реализует интерфейс <xref:System.Collections.IEnumerable>. (Это делается универсальным классом <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.) Чтобы отобразить отдельный объект в коллекции, элемент управления вызывает метод `ToString` объекта для извлечения строки, используемой для представления объекта. В случае <xref:System.TimeZoneInfo> объектов метод `ToString` Возвращает отображаемое имя объекта <xref:System.TimeZoneInfo> (значение его свойства <xref:System.TimeZoneInfo.DisplayName%2A>).

> [!NOTE]
> Поскольку элементы управления "список" вызывают метод `ToString` объекта, можно присвоить элементу управления коллекцию <xref:System.TimeZoneInfo> объектов, иметь элемент управления отображать значимое имя для каждого объекта и получать объект <xref:System.TimeZoneInfo>, который выбрал пользователь. Это избавляет от необходимости извлекать строку для каждого объекта в коллекции, присваивать строке коллекции, которая в свою очередь назначена свойству `DataSource` элемента управления, получать строку, выбранную пользователем, а затем использовать эту строку для извлечения объекта, который он описывает.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- Для импорта следующих пространств имен:

  <xref:System> (в C# коде)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>См. также раздел

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
