---
title: "Практическое руководство. Написание параметров пользователя во время выполнения с помощью C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 274a104d194c9db13d69d2024dc54595690c2ce3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Практическое руководство. Написание параметров пользователя во время выполнения с помощью C# #
Параметры с областью действия приложения доступны только для чтения. Их можно изменить только во время разработки или путем изменения CONFIG-файла между сеансами приложения. Параметры, имеющие область действия пользователя, однако, можно записывать во время выполнения так же, как значение любого свойства. Новое значение сохраняется в течение всего сеанса приложения. Для сохранения изменений параметров между сеансами приложения вызовите метод Save.  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Практическое руководство. Запись и сохранение пользовательских параметров во время выполнения с помощью C#  
  
1.  Получите доступ к параметру и присвойте ему новое значение, как показано в примере ниже.  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  Если необходимо сохранять изменения параметров между сеансами приложения, вызовите метод Save, как показано ниже.  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     Параметры пользователя сохраняются в файле в папке, вложенной в скрытую локальную папку данных приложения.  
  
## <a name="see-also"></a>См. также  
 [Использование параметров приложения и параметров пользователя](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Практическое руководство. Считывание параметров во время выполнения с помощью C#](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
