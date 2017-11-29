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
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="25fa7-102">Практическое руководство. Изменение значение параметра в промежутке между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="25fa7-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="25fa7-103">В некоторых случаях может потребоваться изменить значение параметра между сеансами приложения после компиляции и развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="25fa7-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="25fa7-104">Например может потребоваться изменить строку подключения, чтобы она указывала на правильное расположение базы данных.</span><span class="sxs-lookup"><span data-stu-id="25fa7-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="25fa7-105">Поскольку средства разработки недоступны после компиляции и развертывания приложения, необходимо изменить значение параметра в файле вручную.</span><span class="sxs-lookup"><span data-stu-id="25fa7-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="25fa7-106">Чтобы изменить значение параметра между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="25fa7-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="25fa7-107">С помощью программы "Блокнот" или любой другой текст или XML-редакторе, откройте config-файл, связанный с приложением.</span><span class="sxs-lookup"><span data-stu-id="25fa7-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="25fa7-108">Найдите запись для параметра, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="25fa7-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="25fa7-109">Он должен выглядеть аналогично приведенному ниже примеру.</span><span class="sxs-lookup"><span data-stu-id="25fa7-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="25fa7-110">Введите новое значение для параметра и сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="25fa7-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25fa7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="25fa7-111">See Also</span></span>  
 [<span data-ttu-id="25fa7-112">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="25fa7-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="25fa7-113">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="25fa7-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
