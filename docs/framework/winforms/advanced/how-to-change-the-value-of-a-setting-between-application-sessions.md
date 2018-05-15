---
title: Практическое руководство. Изменение значение параметра в промежутке между сеансами приложения
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 383f72f223fb92170d16a9538c94e67825009abb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="9c071-102">Практическое руководство. Изменение значение параметра в промежутке между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="9c071-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="9c071-103">В некоторых случаях может потребоваться изменить значение параметра между сеансами приложения после компиляции и развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="9c071-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="9c071-104">Например может потребоваться изменить строку подключения, чтобы она указывала на правильное расположение базы данных.</span><span class="sxs-lookup"><span data-stu-id="9c071-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="9c071-105">Поскольку средства разработки недоступны после компиляции и развертывания приложения, необходимо изменить значение параметра в файле вручную.</span><span class="sxs-lookup"><span data-stu-id="9c071-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="9c071-106">Чтобы изменить значение параметра между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="9c071-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="9c071-107">С помощью программы "Блокнот" или любой другой текст или XML-редакторе, откройте config-файл, связанный с приложением.</span><span class="sxs-lookup"><span data-stu-id="9c071-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="9c071-108">Найдите запись для параметра, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="9c071-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="9c071-109">Он должен выглядеть аналогично приведенному ниже примеру.</span><span class="sxs-lookup"><span data-stu-id="9c071-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="9c071-110">Введите новое значение для параметра и сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="9c071-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c071-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9c071-111">See Also</span></span>  
 [<span data-ttu-id="9c071-112">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="9c071-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="9c071-113">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="9c071-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
