---
title: "Практическое руководство. Изменение значение параметра в промежутке между сеансами приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2dff90e499ce421f372137903daf34c09c21d5c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Практическое руководство. Изменение значение параметра в промежутке между сеансами приложения
В некоторых случаях может потребоваться изменить значение параметра между сеансами приложения после компиляции и развертывания приложения. Например может потребоваться изменить строку подключения, чтобы она указывала на правильное расположение базы данных. Поскольку средства разработки недоступны после компиляции и развертывания приложения, необходимо изменить значение параметра в файле вручную.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Чтобы изменить значение параметра между сеансами приложения  
  
1.  С помощью программы "Блокнот" или любой другой текст или XML-редакторе, откройте config-файл, связанный с приложением.  
  
2.  Найдите запись для параметра, который требуется изменить. Он должен выглядеть аналогично приведенному ниже примеру.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Введите новое значение для параметра и сохраните файл.  
  
## <a name="see-also"></a>См. также  
 [Использование параметров приложения и параметров пользователя](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
