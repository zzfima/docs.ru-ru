---
title: "Изменения целевой платформы в .NET Framework 4.5.2 | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2be2a828-9052-4738-a965-d4a836cc6384
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 10af942724ce0207bc6e64f1ebabfdcd2d3488bd
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="retargeting-changes-in-the-net-framework-452"></a>Изменения целевой платформы в .NET Framework 4.5.2
В редких случаях изменения целевой платформы могут повлиять на приложения, которые перекомпилируются для использования в .NET Framework 4.5.2. Если в следующих таблицах не указано иначе, эти изменения не влияют на двоичные файлы, предназначенные для предыдущей версии .NET Framework, но выполняемые в версии 4.5.2. Платформа .NET Framework 4.5.2 включает изменения целевой платформы в следующих областях:  
  
-   [Entity Framework](#EF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="EF"></a>   
## <a name="entity-framework-retargeting-changes"></a>Изменения целевой платформы Entity Framework  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Более простые запросы при использовании операций ограничения без сортировки|Запросы, создающие операторы `JOIN` и содержащие вызов к операции ограничения без предварительного использования <xref:System.Data.Objects.ObjectQuery%601.OrderBy%2A>, теперь создают более простой код SQL. После обновления до [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] эти запросы создают более сложный код SQL, чем предыдущие версии.|Эта функция отключена по умолчанию. Если Entity Framework создает лишние операторы `JOIN`, что ведет к ухудшению производительности, можно включить эту функцию, добавив следующую запись в раздел `<appSettings>` файла конфигурации приложения (app.config):<br /><br /> `<add key="EntityFramework_SimplifyLimitOperations" value="true" />`|Дополнительный номер|  
  
<a name="WinForms"></a>   
## <a name="windows-forms-retargeting-changes"></a>Изменения целевой платформы Windows Forms  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Получение данных в формате HTML из буфера обмена с помощью метода <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName>|Для приложений, предназначенных для [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], а также для выполняющихся в .NET Framework 4.5.1 или более ранних версий, <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> получает HTML-данные в виде строки ASCII. В результате символы, не относящиеся к ASCII (т. е. символы с кодами ASCII больше 0x7F), представляются двумя случайными символами. Например, символ é (0xE9) будет представлен символами Ã© (0xC3 0xA9).<br /><br /> Для приложений, предназначенных для [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] и более поздней версии и выполняемых в .NET Framework 4.5.2, <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> получает HTML-данные в формате UTF-8, который правильно представляет символы с кодами более 0x7F.|Если реализован обходной путь для проблемы с кодировкой HTML-строк (например, явная кодировка HTML-строки, полученной из буфера обмена, путем ее передачи в метод <xref:System.Text.UTF8Encoding.GetString%2A?displayProperty=fullName>), и выполняется изменение целевой платформы приложения с версии 4 на версию 4.5, этот обходной путь необходимо удалить.|Дополнительный номер|  
  
## <a name="see-also"></a>См. также  
 [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-2.md)   
 [Совместимость приложений в 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Совместимость приложений в 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)
