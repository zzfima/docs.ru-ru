---
title: "Как: создание часовых поясов без правил коррекции"
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
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 181d61de62ec9560b46732ad304b4934d4f55fa2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Как: создание часовых поясов без правил коррекции

Точные сведения о часовом поясе, которые требуются для приложения не могут находиться в данной системе по следующим причинам:

* Часовой пояс никогда не был определен в реестре локальной системы.

* Данные о часовом поясе, изменен или удален из реестра.

* Часовой пояс существует, но не точные сведения о коррекции часового пояса для конкретного исторического периода.

В этих случаях можно вызвать <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод, чтобы определить часовой пояс, необходимые для приложения. Создание с или без правил коррекции часового пояса, можно использовать перегрузки этого метода. Если часовой пояс поддерживает летнее время, можно определить с помощью либо правил коррекции фиксированной или плавающей. (Для определения этих терминов см. в разделе «Терминология часовых поясов» [Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Пользовательские часовые пояса путем вызова <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод не добавляются в реестр. Вместо этого они может осуществляться только через ссылку на объект, возвращаемый <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> вызова метода.

В этом разделе показано, как создать часовой пояс без правил коррекции. Чтобы создать часовой пояс, который поддерживает правила коррекции для летнего времени, см. [как: создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>Для создания часовых поясов без правил коррекции

1. Определите отображаемое имя часового пояса.

   Отображаемое имя соответствует стандартному формату, в котором смещение часового пояса от времени в формате UTC заключены в круглые скобки, после чего следует строка, определяющая часовой пояс, один или несколько городов, в часовой пояс или один или несколько частей в курс Книга операций или области в часовом поясе.

2. Укажите имя для зимнего времени часового пояса. Как правило эта строка также используется как идентификатор часового пояса.

3. Если вы хотите использовать другой идентификатор, чем стандартное имя часового пояса, определите идентификатор часового пояса.

4. Создать экземпляр <xref:System.TimeSpan> объект, который определяет смещение часового пояса от времени UTC. Часовые пояса со временем, которые позже времени UTC, имеют положительное смещение. Часовые пояса со временем, предшествующих UTC, имеют отрицательное смещение.

5. Вызовите <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> метод для создания нового часового пояса.

## <a name="example"></a>Пример

В следующем примере определяется пользовательский часовой пояс для Моусон Антарктике, который без правил коррекции.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

Строка, присвоенная <xref:System.TimeZoneInfo.DisplayName%2A> свойства соответствует стандартному формату, в котором смещение часового пояса от времени UTC сопровождается понятным описанием часового пояса.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы ссылка на System.Core.dll была добавлена в проект.

* Что импортируется следующие пространства имен:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md)
[как: создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
