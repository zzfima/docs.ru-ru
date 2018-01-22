---
title: "Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3964551ba2eec0980541e95a7db20ef057a1dd61
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="359ca-102">Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="359ca-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="359ca-103">При разработке и распространение элементов управления, вы можете эти элементы управления отображались в **Выбор элементов панели элементов** dialog box, которое отображается при щелчке правой кнопкой мыши **элементов** и выберите  **Выберите элементы**.</span><span class="sxs-lookup"><span data-stu-id="359ca-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="359ca-104">Можно включить элемент управления для отображения в этом диалоговом окне, используя процедуру регистрации AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="359ca-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="359ca-105">Отображение элемента управления в диалоговом окне Выбор элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="359ca-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="359ca-106">Установите сборку элемента управления в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="359ca-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="359ca-107">Дополнительные сведения см. в разделе [как: Установка сборки в глобальный кэш сборок](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="359ca-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="359ca-108">- или -</span><span class="sxs-lookup"><span data-stu-id="359ca-108">-or-</span></span>  
  
-   <span data-ttu-id="359ca-109">Зарегистрируйте элемент управления и связанных с ней сборок во время разработки, используя процедуру регистрации AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="359ca-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="359ca-110">AssemblyFoldersEx находится в расположении реестра, где сторонние поставщики хранят пути для каждой версии платформы, на которой они поддерживают.</span><span class="sxs-lookup"><span data-stu-id="359ca-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="359ca-111">Разрешение во время разработки можно искать в этом расположении реестра указанные сборки.</span><span class="sxs-lookup"><span data-stu-id="359ca-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="359ca-112">Скрипт реестра может задать элементы управления, которые должны отображаться на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="359ca-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="359ca-113">Дополнительные сведения см. в разделе [развертывание пользовательского элемента управления и сборки времени разработки (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span><span class="sxs-lookup"><span data-stu-id="359ca-113">For more information, see [Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="359ca-114">См. также</span><span class="sxs-lookup"><span data-stu-id="359ca-114">See Also</span></span>  
 [<span data-ttu-id="359ca-115">Диалоговое окно "Выбор элементов панели элементов" (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="359ca-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="359ca-116">Развертывание пользовательского элемента управления и сборки времени разработки (Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="359ca-116">Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)</span></span>](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [<span data-ttu-id="359ca-117">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="359ca-117">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="359ca-118">Практическое руководство. Установка сборки в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="359ca-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [<span data-ttu-id="359ca-119">Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="359ca-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
