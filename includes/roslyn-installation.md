---
ms.openlocfilehash: 2872c5909b382e01fdd231019a12970caa3b77d2
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72526772"
---
## <a name="installation-instructions---visual-studio-installer"></a><span data-ttu-id="35380-101">Инструкции по установке — Visual Studio Installer</span><span class="sxs-lookup"><span data-stu-id="35380-101">Installation instructions - Visual Studio Installer</span></span>

<span data-ttu-id="35380-102">Найти **SDK-пакет .NET Compiler Platform** в **Visual Studio Installer** можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="35380-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-visual-studio-installer---workloads-view"></a><span data-ttu-id="35380-103">Установка с помощью Visual Studio Installer — представление "Рабочие нагрузки"</span><span class="sxs-lookup"><span data-stu-id="35380-103">Install using the Visual Studio Installer - Workloads view</span></span>

<span data-ttu-id="35380-104">SDK-пакет .NET Compiler Platform не выбирается автоматически в рамках рабочей нагрузки разработки расширений Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="35380-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="35380-105">Его необходимо выбрать как дополнительный компонент.</span><span class="sxs-lookup"><span data-stu-id="35380-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="35380-106">Запустите **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="35380-106">Run **Visual Studio Installer**</span></span>
1. <span data-ttu-id="35380-107">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="35380-107">Select **Modify**</span></span>
1. <span data-ttu-id="35380-108">Отметьте рабочую нагрузку **Разработка расширений Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="35380-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="35380-109">Откройте узел **Разработка расширений Visual Studio** в дереве сводки.</span><span class="sxs-lookup"><span data-stu-id="35380-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="35380-110">Установите флажок **SDK-пакет .NET Compiler Platform**.</span><span class="sxs-lookup"><span data-stu-id="35380-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="35380-111">Нужный пакет будет представлен последним в списке дополнительных компонентов.</span><span class="sxs-lookup"><span data-stu-id="35380-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="35380-112">Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:</span><span class="sxs-lookup"><span data-stu-id="35380-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="35380-113">Откройте узел **Отдельные компоненты** в дереве сводки.</span><span class="sxs-lookup"><span data-stu-id="35380-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="35380-114">Установите флажок **Редактор DGML**</span><span class="sxs-lookup"><span data-stu-id="35380-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-visual-studio-installer---individual-components-tab"></a><span data-ttu-id="35380-115">Установка с помощью Visual Studio Installer — вкладка "Отдельные компоненты"</span><span class="sxs-lookup"><span data-stu-id="35380-115">Install using the Visual Studio Installer - Individual components tab</span></span>

1. <span data-ttu-id="35380-116">Запустите **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="35380-116">Run **Visual Studio Installer**</span></span>
1. <span data-ttu-id="35380-117">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="35380-117">Select **Modify**</span></span>
1. <span data-ttu-id="35380-118">Откройте вкладку **Отдельные компоненты**.</span><span class="sxs-lookup"><span data-stu-id="35380-118">Select the **Individual components** tab</span></span>
1. <span data-ttu-id="35380-119">Установите флажок **SDK-пакет .NET Compiler Platform**.</span><span class="sxs-lookup"><span data-stu-id="35380-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="35380-120">Нужный пакет будет представлен в разделе **Компиляторы, средства сборки и среды выполнения** в самом начале.</span><span class="sxs-lookup"><span data-stu-id="35380-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="35380-121">Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:</span><span class="sxs-lookup"><span data-stu-id="35380-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="35380-122">Установите флажок **Редактор DGML**.</span><span class="sxs-lookup"><span data-stu-id="35380-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="35380-123">Нужный пакет будет представлен в разделе **Средства для работы с кодом**.</span><span class="sxs-lookup"><span data-stu-id="35380-123">You'll find it under the **Code tools** section.</span></span>
