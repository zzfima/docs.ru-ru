---
title: "Программирование Windows Forms в Visual Studio с помощью .NET Framework версий 3.0 и 3.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 95348ad57bb4dce1799c1ddf741b69f0e2b969af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a><span data-ttu-id="dc349-102">Программирование Windows Forms в Visual Studio с помощью .NET Framework версий 3.0 и 3.5</span><span class="sxs-lookup"><span data-stu-id="dc349-102">Writing Projects Targeting the .NET Framework 3.0 and 3.5 in Visual Studio 2010</span></span>
<span data-ttu-id="dc349-103">Можно использовать [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] для создания проектов, ориентированных на [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] версии 3.0 и 3.5.</span><span class="sxs-lookup"><span data-stu-id="dc349-103">You can use [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] to create projects that target the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version 3.0 or 3.5.</span></span> <span data-ttu-id="dc349-104">В этом разделе описано выполнение этой задачи.</span><span class="sxs-lookup"><span data-stu-id="dc349-104">This topic describes how to do this.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc349-105">При добавлении действий убедитесь, что задана необходимая версия [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc349-105">When adding activities, make sure that the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] is set.</span></span> <span data-ttu-id="dc349-106">Изменение целевой версии рабочего процесса после добавления действия приведет к ошибке проверки рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dc349-106">Changing the target version of the workflow after activities are added will cause the workflow to fail validation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="dc349-107">Открытие существующих рабочих процессов в [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], включающих действия .Net Framework 3.5, приведет к возникновению ошибки в `this.SetValue()`.</span><span class="sxs-lookup"><span data-stu-id="dc349-107">Opening existing workflows in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] that have .Net Framework 3.5 activities will cause an error at `this.SetValue()`.</span></span> <span data-ttu-id="dc349-108">Чтобы открыть проекты, созданные с помощью предыдущих версий платформы .Net Framework, сначала необходимо открыть пустой рабочий процесс в конструкторе и добавить действие платформы .Net Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="dc349-108">In order to open projects created with previous versions of the .Net Framework, first open a blank workflow in the designer and add a .Net Framework 3.5 activity.</span></span>  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a><span data-ttu-id="dc349-109">Создание проекта платформы .NET Framework 3.0 или 3.5 с помощью Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="dc349-109">To create a .NET Framework  3.0 or 3.5 project with Visual Studio 2010</span></span>  
  
1.  <span data-ttu-id="dc349-110">Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc349-110">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="dc349-111">Выберите **файл**, **новый**, **проекта**.</span><span class="sxs-lookup"><span data-stu-id="dc349-111">Select **File**, **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="dc349-112">В раскрывающемся списке в верхней части диалогового окна выберите необходимую версию [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc349-112">In the drop-down list at the top of the dialog box, select the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a><span data-ttu-id="dc349-113">Обновление целевой версии платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc349-113">To upgrade the targeted version of the .NET Framework</span></span>  
  
1.  <span data-ttu-id="dc349-114">Щелкните правой кнопкой мыши проект в обозревателе решений и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc349-114">Right-click the project in Solution Explorer, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="dc349-115">В **требуемой версии .NET Framework** раскрывающегося списка выберите необходимую версию.</span><span class="sxs-lookup"><span data-stu-id="dc349-115">In the **Target Framework** drop-down list, select the desired version.</span></span>
