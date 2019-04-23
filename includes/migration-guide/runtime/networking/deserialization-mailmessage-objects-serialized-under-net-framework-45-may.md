---
ms.openlocfilehash: a6f93bbdf39a1b525e2daeb12afc3a6392a66e30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235953"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>Десериализация объектов MailMessage, сериализованных в .NET Framework 4.5, может завершиться сбоем

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.5, объекты <xref:System.Web.Mail.MailMessage> могут содержать символы, отличные от ASCII. В .NET Framework 4 поддерживаются только символы ASCII. В .NET Framework 4 не могут быть десериализованы объекты <xref:System.Web.Mail.MailMessage>, содержащие отличные от ASCII символы и сериализованные в .NET Framework 4.5 или более поздней версии.|
|Предложение|Убедитесь, что в коде реализована обработка исключений при десериализации объекта <xref:System.Web.Mail.MailMessage>.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
