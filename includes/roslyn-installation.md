---
ms.openlocfilehash: 72acd0029d0189de1c724856572957f111b9d18f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804953"
---
## <a name="installation-instructions"></a><span data-ttu-id="1f068-101">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="1f068-101">Installation instructions</span></span> 

<span data-ttu-id="1f068-102">Найти **SDK-пакет .NET Compiler Platform** в **Visual Studio Installer** можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="1f068-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-workloads-view"></a><span data-ttu-id="1f068-103">Установка с помощью представления рабочих нагрузок</span><span class="sxs-lookup"><span data-stu-id="1f068-103">Install using the Workloads view</span></span>

<span data-ttu-id="1f068-104">SDK-пакет .NET Compiler Platform не выбирается автоматически в рамках рабочей нагрузки разработки расширений Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f068-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="1f068-105">Его необходимо выбрать как дополнительный компонент.</span><span class="sxs-lookup"><span data-stu-id="1f068-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="1f068-106">Запустите **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="1f068-106">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="1f068-107">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1f068-107">Select **Modify**</span></span> 
1. <span data-ttu-id="1f068-108">Отметьте рабочую нагрузку **Разработка расширений Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="1f068-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="1f068-109">Откройте узел **Разработка расширений Visual Studio** в дереве сводки.</span><span class="sxs-lookup"><span data-stu-id="1f068-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="1f068-110">Установите флажок **SDK-пакет .NET Compiler Platform**.</span><span class="sxs-lookup"><span data-stu-id="1f068-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="1f068-111">Нужный пакет будет представлен последним в списке дополнительных компонентов.</span><span class="sxs-lookup"><span data-stu-id="1f068-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="1f068-112">Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:</span><span class="sxs-lookup"><span data-stu-id="1f068-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="1f068-113">Откройте узел **Отдельные компоненты** в дереве сводки.</span><span class="sxs-lookup"><span data-stu-id="1f068-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="1f068-114">Установите флажок **Редактор DGML**</span><span class="sxs-lookup"><span data-stu-id="1f068-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-individual-components-tab"></a><span data-ttu-id="1f068-115">Установка с использованием вкладки "Отдельные компоненты"</span><span class="sxs-lookup"><span data-stu-id="1f068-115">Install using the Individual components tab</span></span>

1. <span data-ttu-id="1f068-116">Запустите **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="1f068-116">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="1f068-117">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1f068-117">Select **Modify**</span></span> 
1. <span data-ttu-id="1f068-118">Откройте вкладку **Отдельные компоненты**.</span><span class="sxs-lookup"><span data-stu-id="1f068-118">Select the **Individual components** tab</span></span> 
1. <span data-ttu-id="1f068-119">Установите флажок **SDK-пакет .NET Compiler Platform**.</span><span class="sxs-lookup"><span data-stu-id="1f068-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="1f068-120">Нужный пакет будет представлен в разделе **Компиляторы, средства сборки и среды выполнения** в самом начале.</span><span class="sxs-lookup"><span data-stu-id="1f068-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="1f068-121">Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:</span><span class="sxs-lookup"><span data-stu-id="1f068-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="1f068-122">Установите флажок **Редактор DGML**.</span><span class="sxs-lookup"><span data-stu-id="1f068-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="1f068-123">Нужный пакет будет представлен в разделе **Средства для работы с кодом**.</span><span class="sxs-lookup"><span data-stu-id="1f068-123">You'll find it under the **Code tools** section.</span></span>
