---
title: 'Как выполнить: Измените значение параметра между сеансами приложения'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: c1626cea581e5c180665d0ce805dea3e67f27a05
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714363"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="f2327-102">Как выполнить: Измените значение параметра между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="f2327-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="f2327-103">В некоторых случаях может потребоваться изменить значение параметра между сеансами приложения после компиляции и развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="f2327-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="f2327-104">Например может потребоваться изменить строку подключения, чтобы он указывал на правильное расположение базы данных.</span><span class="sxs-lookup"><span data-stu-id="f2327-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="f2327-105">Так как средства разработки недоступны после компиляции и развертывания приложения, необходимо изменить значение параметра в соответствующем файле вручную.</span><span class="sxs-lookup"><span data-stu-id="f2327-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="f2327-106">Чтобы изменить значение параметра между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="f2327-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="f2327-107">В Блокнот (Майкрософт) или некоторые другие текстовом редакторе или редакторе XML, откройте файл .config, связанный с приложением.</span><span class="sxs-lookup"><span data-stu-id="f2327-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="f2327-108">Найдите запись для параметра, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="f2327-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="f2327-109">Он должен выглядеть аналогично приведенному ниже примеру.</span><span class="sxs-lookup"><span data-stu-id="f2327-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="f2327-110">Введите новое значение параметра и сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="f2327-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2327-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f2327-111">See also</span></span>
- [<span data-ttu-id="f2327-112">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="f2327-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="f2327-113">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="f2327-113">Application Settings Overview</span></span>](application-settings-overview.md)
