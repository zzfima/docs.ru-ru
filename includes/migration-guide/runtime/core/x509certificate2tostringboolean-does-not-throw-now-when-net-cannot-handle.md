---
ms.openlocfilehash: 0dfc87201b9b31cd9d936f2c965c7d0ca0140cab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774175"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>Теперь метод X509Certificate2.ToString(Boolean) не создает исключение, когда .NET не удается обработать сертификат

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5.2 и более ранних версиях этот метод создавал исключение, если значение <code>true</code> передавалось в параметр verbose и были установлены сертификаты, не поддерживаемые .NET Framework. Теперь метод будет выполняться успешно и возвращать допустимую строку, в которой пропущены недоступные части сертификата.|
|Предложение|Любой код, зависящий от <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>, следует обновить для ожидания того, что в некоторых случаях, когда ранее API возвращал исключение, в возвращаемой строке могут отсутствовать некоторые данные сертификата (например, открытый ключ, закрытый ключ и расширения).|
|Область|Пограничный случай|
|Версия|4.6|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
