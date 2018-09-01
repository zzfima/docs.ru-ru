---
title: Практическое руководство. Определение строки подключения
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: f40b8bc68eda1cb4b64b34d12b2922da69929203
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387758"
---
# <a name="how-to-define-the-connection-string"></a>Практическое руководство. Определение строки подключения
В этом разделе показано, как определить строку соединения, используемую при подключении к концептуальной модели. Этот раздел основан на [AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) концептуальной модели. Модель AdventureWorks Sales используется во всех разделах документации платформы [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], связанных с выполнением задач. В этом разделе предполагается, что вы уже настроили [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] и определенные в модели AdventureWorks Sales. Дополнительные сведения см. в разделе [как: определение модели и сопоставления файлов вручную](https://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a). Процедуры этого раздела также включены в [как: вручную настроить проект Entity Framework](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Если вы используете [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] мастера в проект Visual Studio, он автоматически сформирует EDMX-файл и настроит проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [как: использовать мастер моделей EDM](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>Определение строки соединения Entity Framework  
  
-   Откройте файл конфигурации приложения (app.config) и добавьте следующую строку соединения:  
  
  
  
     Если проект не имеет файла конфигурации приложения, можно добавить его, выбрав **Добавление нового элемента** из **проекта** меню, выбрав **Общие** категории выбрав **файла конфигурации приложения**и выбрав **добавить**.  
  
## <a name="see-also"></a>См. также  
 [Краткое руководство](https://msdn.microsoft.com/library/0bc534be-789f-4819-b9f6-76e51d961675)  
 [Практическое: создать новый EDMX-файл](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2)  
 [Средства работы с моделью EDM ADO.NET](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
