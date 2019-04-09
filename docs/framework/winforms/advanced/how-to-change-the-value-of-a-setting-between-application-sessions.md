---
title: 'Как выполнить: Изменение значения параметра между сеансами приложения'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 03a10e95362b1d49e4929c07ab6193f53898d34f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142861"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="36f3f-102">Как выполнить: Изменение значения параметра между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="36f3f-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="36f3f-103">В некоторых случаях может потребоваться изменить значение параметра между сеансами приложения после компиляции и развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="36f3f-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="36f3f-104">Например может потребоваться изменить строку подключения, чтобы он указывал на правильное расположение базы данных.</span><span class="sxs-lookup"><span data-stu-id="36f3f-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="36f3f-105">Так как средства разработки недоступны после компиляции и развертывания приложения, необходимо изменить значение параметра в соответствующем файле вручную.</span><span class="sxs-lookup"><span data-stu-id="36f3f-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="36f3f-106">Чтобы изменить значение параметра между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="36f3f-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="36f3f-107">В Блокнот (Майкрософт) или некоторые другие текстовом редакторе или редакторе XML, откройте файл .config, связанный с приложением.</span><span class="sxs-lookup"><span data-stu-id="36f3f-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="36f3f-108">Найдите запись для параметра, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="36f3f-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="36f3f-109">Он должен выглядеть аналогично приведенному ниже примеру.</span><span class="sxs-lookup"><span data-stu-id="36f3f-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="36f3f-110">Введите новое значение параметра и сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="36f3f-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f3f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="36f3f-111">See also</span></span>

- [<span data-ttu-id="36f3f-112">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="36f3f-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="36f3f-113">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="36f3f-113">Application Settings Overview</span></span>](application-settings-overview.md)
