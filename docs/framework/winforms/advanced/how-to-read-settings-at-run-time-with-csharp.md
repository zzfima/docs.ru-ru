---
title: "Практическое руководство. Считывание параметров во время выполнения с помощью C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c23fd88d33ff4ca480c435f2058f4c568320578
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="f25cf-102">Практическое руководство. Считывание параметров во время выполнения с помощью C#</span><span class="sxs-lookup"><span data-stu-id="f25cf-102">How To: Read Settings at Run Time With C#</span></span> #
<span data-ttu-id="f25cf-103">Параметры области приложения и параметры области пользователя можно считывать во время выполнения с помощью объекта "Свойства".</span><span class="sxs-lookup"><span data-stu-id="f25cf-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="f25cf-104">Объект "Свойства" предоставляет все параметры по умолчанию для проекта через элемент Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="f25cf-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member.</span></span>  
  
### <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="f25cf-105">Считывание параметров во время выполнения с помощью C#</span><span class="sxs-lookup"><span data-stu-id="f25cf-105">To Read Settings at Run Time with C#</span></span>  
  
-   <span data-ttu-id="f25cf-106">Доступ к соответствующему параметру через элемент Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="f25cf-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="f25cf-107">В следующем примере показано, как назначить параметр с именем `myColor` свойству BackColor.</span><span class="sxs-lookup"><span data-stu-id="f25cf-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="f25cf-108">Необходимо наличие ранее созданного файла параметров, содержащего параметр с именем `myColor` и типом `System.Drawing.Color`.</span><span class="sxs-lookup"><span data-stu-id="f25cf-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="f25cf-109">Сведения о создании файла параметров см. в разделе [How To: создать новый параметр во время разработки](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="f25cf-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f25cf-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f25cf-110">See Also</span></span>  
 [<span data-ttu-id="f25cf-111">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="f25cf-111">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="f25cf-112">Практическое руководство. Написание параметров пользователя во время выполнения с помощью C#</span><span class="sxs-lookup"><span data-stu-id="f25cf-112">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
 [<span data-ttu-id="f25cf-113">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="f25cf-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
