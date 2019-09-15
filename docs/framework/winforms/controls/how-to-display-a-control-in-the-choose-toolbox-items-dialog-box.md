---
title: Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f52c1d127df8f0e831db0749e3453bb1c54d5886
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972067"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="2053f-102">Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="2053f-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>

<span data-ttu-id="2053f-103">При разработке и распространении элементов управления может потребоваться, чтобы они отображались в диалоговом окне **Выбор элементов панели элементов** Visual Studio, которое отображается, если щелкнуть правой кнопкой мыши **панель элементов** и выбрать пункт **выбрать элементы**.</span><span class="sxs-lookup"><span data-stu-id="2053f-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box of Visual Studio, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="2053f-104">Можно включить отображение элемента управления в этом диалоговом окне с помощью процедуры регистрации AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="2053f-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>

<span data-ttu-id="2053f-105">Для вывода элемента управления в диалоговом окне Выбор элементов панели элементов выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2053f-105">To display your control in the Choose Toolbox Items dialog box:</span></span>

- <span data-ttu-id="2053f-106">Установите сборку элемента управления в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="2053f-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="2053f-107">Дополнительные сведения см. в разделе [Практическое руководство. Установка сборки в глобальный кэш сборок](../../app-domains/install-assembly-into-gac.md)</span><span class="sxs-lookup"><span data-stu-id="2053f-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/install-assembly-into-gac.md)</span></span>

  <span data-ttu-id="2053f-108">-или-</span><span class="sxs-lookup"><span data-stu-id="2053f-108">-or-</span></span>

- <span data-ttu-id="2053f-109">Зарегистрируйте элемент управления и связанные с ним сборки времени разработки с помощью процедуры регистрации AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="2053f-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="2053f-110">AssemblyFoldersEx — это расположение реестра, в котором сторонние поставщики хранят пути для каждой поддерживаемой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="2053f-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="2053f-111">Разрешение во время разработки может найти в этом расположении реестра сведения о ссылочных сборках.</span><span class="sxs-lookup"><span data-stu-id="2053f-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="2053f-112">Скрипт реестра может указывать элементы управления, которые должны отображаться на панели элементов.</span><span class="sxs-lookup"><span data-stu-id="2053f-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="2053f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2053f-113">See also</span></span>

- [<span data-ttu-id="2053f-114">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="2053f-114">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="2053f-115">Практическое руководство. Установка сборки в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="2053f-115">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/install-assembly-into-gac.md)
- [<span data-ttu-id="2053f-116">Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="2053f-116">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
