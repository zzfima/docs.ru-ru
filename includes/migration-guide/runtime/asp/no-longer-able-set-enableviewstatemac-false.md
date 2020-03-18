---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803246"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a>Свойству EnableViewStateMac больше невозможно задавать значение false

|   |   |
|---|---|
|Подробнее|ASP.NET теперь не позволяет разработчикам указывать <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> или <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>. Код проверки подлинности сообщения (MAC) состояния просмотра теперь принудительно применяется для всех запросов со встроенным состоянием просмотра. Затрагиваются только те приложения, в которых для свойства EnableViewStateMac явно задано значение <code>false</code>.|
|Предложение|Следует считать, что свойство EnableViewStateMac имеет значение true, и возникающие ошибки MAC должны быть устранены (как описано в [этом](https://support.microsoft.com/kb/2915218) руководстве, содержащем несколько решений в зависимости от причины ошибки MAC).|
|Область|Значительно|
|Version|4.5.2|
|Type|Параметры выполнения|
