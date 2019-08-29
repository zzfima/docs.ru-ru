---
title: Практическое руководство. Создание часовых поясов без правил коррекции
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 510112c8b19ec002d1dcf918eb983b55dee68fd0
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106660"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Практическое руководство. Создание часовых поясов без правил коррекции

Точные сведения о часовом поясе, необходимые для приложения, могут отсутствовать в определенной системе по нескольким причинам:

- Часовой пояс никогда не был определен в реестре локальной системы.

- Данные о часовом поясе были изменены или удалены из реестра.

- Часовой пояс существует, но не содержит достоверных сведений о корректировках часового пояса для определенного периода предыстории.

В таких случаях можно вызвать <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод, чтобы определить часовой пояс, необходимый для приложения. Перегрузки этого метода можно использовать для создания часового пояса с правилами коррекции или без них. Если часовой пояс поддерживает переход на летнее время, можно определить корректировки с помощью фиксированных или плавающих правил коррекции. (Определения этих терминов см. в подразделе «терминология часовых поясов» раздела « [Общие сведения о](../../../docs/standard/datetime/time-zone-overview.md)часовом поясе».)

> [!IMPORTANT]
> Пользовательские часовые пояса, созданные путем <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> вызова метода, не добавляются в реестр. Вместо этого доступ к ним можно получить только через ссылку на объект, <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> возвращенную вызовом метода.

В этом разделе показано, как создать часовой пояс без правил коррекции. Сведения о создании часового пояса, поддерживающего правила коррекции летнего времени [, см. в разделе как Создание часовых поясов с правилами](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)коррекции.

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>Создание часового пояса без правил коррекции

1. Определите отображаемое имя часового пояса.

   Отображаемое имя соответствует довольно стандартному формату, в котором смещение часового пояса относительно времени в формате UTC заключено в круглые скобки. за ним следует строка, определяющая часовой пояс, один или несколько городов в часовом поясе или один или несколько из КАУ. нтриес или регионы в часовом поясе.

2. Определите имя стандартного времени часового пояса. Как правило, эта строка также используется в качестве идентификатора часового пояса.

3. Если вы хотите использовать другой идентификатор, отличный от стандартного имени часового пояса, определите идентификатор часового пояса.

4. Создайте экземпляр объекта, который определяет смещение часового пояса относительно времени в формате UTC. <xref:System.TimeSpan> Часовые пояса со временем, превышающим время UTC, имеют положительное смещение. Часовые пояса со временем, предшествующим UTC, имеют отрицательное смещение.

5. Вызовите <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> метод, чтобы создать экземпляр нового часового пояса.

## <a name="example"></a>Пример

В следующем примере определяется пользовательский часовой пояс для Моусон, Антарктида, для которого не заданы правила коррекции.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

Строка, назначенная <xref:System.TimeZoneInfo.DisplayName%2A> свойству, соответствует стандартному формату, в котором за смещение часового пояса от времени UTC следует понятное описание часового пояса.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- Для импорта следующих пространств имен:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md)
- [Практическое руководство. Создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
