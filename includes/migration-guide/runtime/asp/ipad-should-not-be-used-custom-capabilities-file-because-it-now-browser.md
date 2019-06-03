---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379580"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a>Не следует использовать iPad в файле пользовательских возможностей, так как теперь это функция браузера

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.5 iPad является идентификатором в файле возможностей браузера ASP.NET по умолчанию, поэтому его не следует использовать в файле пользовательских возможностей|
|Предложение|Если требуются определенные возможности iPad, необходимо изменить поведение iPad, настроив возможности на предварительно определенном шлюзе refID &quot;IPad&quot; или создав новый идентификатор &quot;IPad&quot; путем сопоставления агента пользователя.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
