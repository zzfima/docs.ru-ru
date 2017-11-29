---
title: "Практическое руководство. Определение строки подключения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 757b70d99a7f2b499d4ad5aab2be2bb61b28af0d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-the-connection-string"></a>Практическое руководство. Определение строки подключения
В этом разделе показано, как определить строку соединения, используемую при подключении к концептуальной модели. В этом разделе основан на [AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) концептуальной модели. Модель AdventureWorks Sales используется во всех разделах документации платформы [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], связанных с выполнением задач. В этом разделе предполагается, что вы уже настроили [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] и определенные модели AdventureWorks Sales. Дополнительные сведения см. в разделе [как: определение модели и сопоставления файлов вручную](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a). Процедуры, описанные в этом разделе также включаются в [как: вручную настроить проект Entity Framework](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  При использовании мастера [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] в проекте [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] он автоматически сформирует EDMX-файл и настроит проект для использования платформы [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [как: использовать мастер моделей EDM](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>Определение строки соединения Entity Framework  
  
-   Откройте файл конфигурации приложения (app.config) и добавьте следующую строку соединения:  
  
  
  
     Если проект не имеет файла конфигурации приложения, можно добавить его, выбрав **Добавление нового элемента** из **проекта** меню, при выборе **Общие** категории При выборе **файла конфигурации приложения**и выбрав **добавить**.  
  
## <a name="see-also"></a>См. также  
 [Краткое руководство](http://msdn.microsoft.com/en-us/0bc534be-789f-4819-b9f6-76e51d961675)  
 [Как: Создание нового EDMX-файла](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2)  
 [Средства работы с моделью EDM ADO.NET](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
