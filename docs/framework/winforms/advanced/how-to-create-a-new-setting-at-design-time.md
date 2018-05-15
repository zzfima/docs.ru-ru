---
title: Практическое руководство. Создание новых параметров во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 618355948578bd8f15e8cf7bec6f599e3169b77a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="6de34-102">Практическое руководство. Создание новых параметров во время разработки</span><span class="sxs-lookup"><span data-stu-id="6de34-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="6de34-103">Можно создать новый параметр во время разработки с помощью конструктора параметров.</span><span class="sxs-lookup"><span data-stu-id="6de34-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="6de34-104">Конструктор параметров является интерфейсом стиль сетки, который позволяет создавать новые параметры и указывать свойства для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="6de34-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="6de34-105">Необходимо указать имя, значение, тип и область для новых параметров.</span><span class="sxs-lookup"><span data-stu-id="6de34-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="6de34-106">После создания параметр становится доступен в коде.</span><span class="sxs-lookup"><span data-stu-id="6de34-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="6de34-107">Чтобы создать новый параметр во время разработки в C#</span><span class="sxs-lookup"><span data-stu-id="6de34-107">To create a new setting at design time in C#</span></span>  
  
1.  <span data-ttu-id="6de34-108">В **обозревателе решений**, разверните **свойства** узле проекта.</span><span class="sxs-lookup"><span data-stu-id="6de34-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2.  <span data-ttu-id="6de34-109">Дважды щелкните файл с расширением Settings, в которой требуется добавить новый параметр.</span><span class="sxs-lookup"><span data-stu-id="6de34-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="6de34-110">Является именем по умолчанию для этого файла Settings.settings.</span><span class="sxs-lookup"><span data-stu-id="6de34-110">The default name for this file is Settings.settings.</span></span>  
  
3.  <span data-ttu-id="6de34-111">В конструкторе параметров задайте имя, значение, тип и область для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="6de34-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="6de34-112">Каждая строка представляет один параметр.</span><span class="sxs-lookup"><span data-stu-id="6de34-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="6de34-113">Чтобы создать новый параметр во время разработки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6de34-113">To create a new setting at design time in Visual Basic</span></span>  
  
1.  <span data-ttu-id="6de34-114">В **обозревателе решений**, щелкните правой кнопкой мыши узел проекта и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="6de34-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="6de34-115">В **свойства** выберите **параметры** вкладки.</span><span class="sxs-lookup"><span data-stu-id="6de34-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3.  <span data-ttu-id="6de34-116">В конструкторе параметров задайте имя, значение, тип и область для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="6de34-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="6de34-117">Каждая строка представляет один параметр.</span><span class="sxs-lookup"><span data-stu-id="6de34-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de34-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6de34-118">See Also</span></span>  
 [<span data-ttu-id="6de34-119">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="6de34-119">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="6de34-120">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="6de34-120">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="6de34-121">Практическое руководство. Изменение значения существующего параметра во время разработки</span><span class="sxs-lookup"><span data-stu-id="6de34-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)
