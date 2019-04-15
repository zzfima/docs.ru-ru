---
ms.openlocfilehash: 74f00821f2304664729faa8de2f0163c6611f513
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235887"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a>Данные, записанные в PrintSystemJobInfo.JobStream, должны иметь формат XPS

|   |   |
|---|---|
|Подробные сведения|Свойство <xref:System.Printing.PrintSystemJobInfo.JobStream> предоставляет поток задания печати. Пользователь может отправить необработанные данные в компоненты печати базовой операционной системы путем записи в этот поток. Начиная с .NET Framework 4.5 в Windows 8 и более поздних версиях операционной системы Windows данные, которые записываются в этот поток, должны быть в формате XPS, как поток пакета.|
|Предложение|Для вывода содержимого печати выполните одно из следующих действий.<ul><li>Используйте класс <xref:System.Windows.Xps.XpsDocumentWriter> класса для вывода содержимого печати. Это рекомендуемый вариант.</li><li>Убедитесь, что данные, отправляемые в поток, возвращенный свойством <xref:System.Printing.PrintSystemJobInfo.JobStream>, находятся в формате XPS, как поток пакета.</li></ul>|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|
