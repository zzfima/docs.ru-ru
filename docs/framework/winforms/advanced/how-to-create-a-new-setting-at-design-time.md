---
title: "Практическое руководство. Создание новых параметров во время разработки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04b86579f45c5a357f8759bf36ae41f7a5c6e98b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="df035-102">Практическое руководство. Создание новых параметров во время разработки</span><span class="sxs-lookup"><span data-stu-id="df035-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="df035-103">Можно создать новый параметр во время разработки с помощью конструктора параметров.</span><span class="sxs-lookup"><span data-stu-id="df035-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="df035-104">Конструктор параметров является интерфейсом стиль сетки, который позволяет создавать новые параметры и указывать свойства для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="df035-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="df035-105">Необходимо указать имя, значение, тип и область для новых параметров.</span><span class="sxs-lookup"><span data-stu-id="df035-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="df035-106">После создания параметр становится доступен в коде.</span><span class="sxs-lookup"><span data-stu-id="df035-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="df035-107">Чтобы создать новый параметр во время разработки в C#</span><span class="sxs-lookup"><span data-stu-id="df035-107">To create a new setting at design time in C#</span></span>  
  
1.  <span data-ttu-id="df035-108">В **обозревателе решений**, разверните **свойства** узле проекта.</span><span class="sxs-lookup"><span data-stu-id="df035-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2.  <span data-ttu-id="df035-109">Дважды щелкните файл с расширением Settings, в которой требуется добавить новый параметр.</span><span class="sxs-lookup"><span data-stu-id="df035-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="df035-110">Является именем по умолчанию для этого файла Settings.settings.</span><span class="sxs-lookup"><span data-stu-id="df035-110">The default name for this file is Settings.settings.</span></span>  
  
3.  <span data-ttu-id="df035-111">В конструкторе параметров задайте имя, значение, тип и область для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="df035-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="df035-112">Каждая строка представляет один параметр.</span><span class="sxs-lookup"><span data-stu-id="df035-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="df035-113">Чтобы создать новый параметр во время разработки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df035-113">To create a new setting at design time in Visual Basic</span></span>  
  
1.  <span data-ttu-id="df035-114">В **обозревателе решений**, щелкните правой кнопкой мыши узел проекта и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="df035-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="df035-115">В **свойства** выберите **параметры** вкладки.</span><span class="sxs-lookup"><span data-stu-id="df035-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3.  <span data-ttu-id="df035-116">В конструкторе параметров задайте имя, значение, тип и область для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="df035-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="df035-117">Каждая строка представляет один параметр.</span><span class="sxs-lookup"><span data-stu-id="df035-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df035-118">См. также</span><span class="sxs-lookup"><span data-stu-id="df035-118">See Also</span></span>  
 [<span data-ttu-id="df035-119">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="df035-119">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="df035-120">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="df035-120">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="df035-121">Практическое руководство. Изменение значения существующего параметра во время разработки</span><span class="sxs-lookup"><span data-stu-id="df035-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)
