---
title: "Как: перечисление часовых поясов, присутствующих на компьютере"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f77afc8a0f2e6c110f4dc037c12ecc8b06908e60
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Как: перечисление часовых поясов, присутствующих на компьютере

Для успешной работы с указанным часовым поясом необходимо, чтобы сведения об этом часовом поясе были доступны в системе. В операционных системах Windows XP и Windows Vista сохранить эту информацию в реестре. Тем не менее, хотя общее число часовых поясов, которые существуют по всему миру, велико, реестр содержит сведения только о подмножестве из них. Кроме того, реестр сам является динамической структурой, содержимое которой подвержено преднамеренным и случайным изменениям. В итоге приложение не может всегда предполагать, что конкретный часовой пояс определен и доступен в системе. Первым шагом для многих приложений, использующих данные о часовых поясах, является определение доступности требуемого часового пояса на локальном компьютере или предоставление пользователю списка часовых поясов для выбора. Для этого необходимо, чтобы приложение перечислило часовые пояса, определенные в локальной системе.

> [!NOTE]
> Если приложение зависит от наличия определенного часового пояса, не могут быть определены в локальной системе, приложение может проверить его наличие, сериализацию и десериализацию сведений о часовом поясе. Часовой пояс можно добавить элемент управления списка, затем, чтобы пользователь приложения можно выбрать его. Дополнительные сведения см. в разделе [как: сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) и [как: восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Перечисление часовых поясов, присутствующих в локальной системе

1. Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. Метод возвращает универсальный <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию <xref:System.TimeZoneInfo> объектов. Элементы коллекции сортируются по их <xref:System.TimeZoneInfo.DisplayName%2A> свойство. Пример:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Перечислите отдельные <xref:System.TimeZoneInfo> объектов в коллекции с помощью `foreach` (в C#) или `For Each`...`Next` цикл (в Visual Basic) и выполните все необходимые действия для каждого объекта. Например, следующий код перечисляет <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию <xref:System.TimeZoneInfo> объектов возвращенную на шаге 1 и перечислены отображаемое имя каждого часового пояса на консоль.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Чтобы предоставить пользователю список часовых поясов, присутствующих в локальной системе

1. Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. Метод возвращает универсальный <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию <xref:System.TimeZoneInfo> объектов.

2. Назначить коллекцию, возвращенную на шаге 1, `DataSource` свойство Windows forms или ASP.NET списка элемента управления.

3. Получить <xref:System.TimeZoneInfo> объект, выбранный пользователем.

Приведен пример для приложения Windows.

## <a name="example"></a>Пример

В примере запускается приложение Windows, отображает часовые пояса, определенные в системе, в поле со списком. Затем отображается диалоговое окно, содержащее значение <xref:System.TimeZoneInfo.DisplayName%2A> свойства объекта часового пояса, выбранного пользователем.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Наиболее список элементов управления (таких как <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> или <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> управления) для присвоения коллекцию объектные переменные, их `DataSource` при условии, что коллекция реализует свойство <xref:System.Collections.IEnumerable> интерфейса. (Универсальный <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> класса делает это.) Чтобы отобразить отдельный объект в коллекции, элемент управления вызывает этот объект `ToString` метод для извлечения строки, которая используется для представления объекта. В случае использования <xref:System.TimeZoneInfo> объектов, `ToString` возвращает <xref:System.TimeZoneInfo> отображаемое имя объекта (значение его <xref:System.TimeZoneInfo.DisplayName%2A> свойство).

> [!NOTE]
> Так как элементы управления списком вызов объекта `ToString` метод, можно назначить коллекцию <xref:System.TimeZoneInfo> объектов с элементом управления, установить элемент управления отображать понятное имя для каждого объекта и получить <xref:System.TimeZoneInfo> объект, выбранный пользователем. Это избавляет от необходимости извлекать строку для каждого объекта в коллекции, назначьте строку коллекции, в свою очередь назначенный к элементу управления `DataSource` свойство, получения строки, выбранном пользователем, а затем использовать эту строку для извлечения объекта Описывает, что он. 

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы ссылка на System.Core.dll была добавлена в проект.

* Что импортируется следующие пространства имен:

  <xref:System>(в коде C#)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[как: сохранение часовых поясов во внедренный ресурс](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[как: восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
