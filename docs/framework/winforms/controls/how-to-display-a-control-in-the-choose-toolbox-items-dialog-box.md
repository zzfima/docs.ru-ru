---
title: Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: d504ace9e5571246ae0e78e165a7ad2bc23fa481
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954231"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="64f3a-102">Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="64f3a-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="64f3a-103">При разработке и распределить элементы управления, вы можете эти элементы управления отображались в **Выбор элементов панели элементов** диалоговое окно, которое отображается при щелчке правой кнопкой мыши **элементов** и выберите  **Выбор элементов**.</span><span class="sxs-lookup"><span data-stu-id="64f3a-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="64f3a-104">Вы можете включить элемент управления появился в этом диалоговом окне, используя процедуру регистрации AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="64f3a-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="64f3a-105">Отображение элемента управления в диалоговом окне Выбор элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="64f3a-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
- <span data-ttu-id="64f3a-106">Установите сборку элемента управления в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="64f3a-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="64f3a-107">Дополнительные сведения см. в разделе [Как Установка сборки в глобальный кэш сборок](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="64f3a-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="64f3a-108">-или-</span><span class="sxs-lookup"><span data-stu-id="64f3a-108">-or-</span></span>  
  
- <span data-ttu-id="64f3a-109">Зарегистрируйте элемент управления и его связанные сборки времени разработки, используя процедуру регистрации AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="64f3a-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="64f3a-110">AssemblyFoldersEx находится в расположении реестра, где сторонние поставщики сохраняют пути для каждой версии платформы, на которой они поддерживают.</span><span class="sxs-lookup"><span data-stu-id="64f3a-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="64f3a-111">Разрешение во время разработки можно искать в этом расположении реестра поиск эталонных сборок.</span><span class="sxs-lookup"><span data-stu-id="64f3a-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="64f3a-112">Скрипт реестра можно указать элементы управления, которые должны отображаться на панели элементов.</span><span class="sxs-lookup"><span data-stu-id="64f3a-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="64f3a-113">Дополнительные сведения см. в разделе [развертывание пользовательского элемента управления и сборки времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="64f3a-113">For more information, see [Deploying a Custom Control and Design-time Assemblies](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f3a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="64f3a-114">See also</span></span>

- <span data-ttu-id="64f3a-115">[Диалоговое окно "Выбор элементов панели элементов" (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="64f3a-115">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- <span data-ttu-id="64f3a-116">[Развертывание пользовательского элемента управления и сборки времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="64f3a-116">[Deploying a Custom Control and Design-time Assemblies](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))</span></span>
- [<span data-ttu-id="64f3a-117">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="64f3a-117">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="64f3a-118">Практическое руководство. Установка сборки в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="64f3a-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [<span data-ttu-id="64f3a-119">Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="64f3a-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
