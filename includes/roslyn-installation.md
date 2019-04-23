---
ms.openlocfilehash: 72acd0029d0189de1c724856572957f111b9d18f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675900"
---
## <a name="installation-instructions"></a><span data-ttu-id="27925-101">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="27925-101">Installation instructions</span></span> 

<span data-ttu-id="27925-102">Найти **SDK-пакет .NET Compiler Platform** в **Visual Studio Installer** можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="27925-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-workloads-view"></a><span data-ttu-id="27925-103">Установка с помощью представления рабочих нагрузок</span><span class="sxs-lookup"><span data-stu-id="27925-103">Install using the Workloads view</span></span>

<span data-ttu-id="27925-104">SDK-пакет .NET Compiler Platform не выбирается автоматически в рамках рабочей нагрузки разработки расширений Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="27925-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="27925-105">Его необходимо выбрать как дополнительный компонент.</span><span class="sxs-lookup"><span data-stu-id="27925-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="27925-106">Запустите **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="27925-106">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="27925-107">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="27925-107">Select **Modify**</span></span> 
1. <span data-ttu-id="27925-108">Отметьте рабочую нагрузку **Разработка расширений Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="27925-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="27925-109">Откройте узел **Разработка расширений Visual Studio** в дереве сводки.</span><span class="sxs-lookup"><span data-stu-id="27925-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="27925-110">Установите флажок **SDK-пакет .NET Compiler Platform**.</span><span class="sxs-lookup"><span data-stu-id="27925-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="27925-111">Нужный пакет будет представлен последним в списке дополнительных компонентов.</span><span class="sxs-lookup"><span data-stu-id="27925-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="27925-112">Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:</span><span class="sxs-lookup"><span data-stu-id="27925-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="27925-113">Откройте узел **Отдельные компоненты** в дереве сводки.</span><span class="sxs-lookup"><span data-stu-id="27925-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="27925-114">Установите флажок **Редактор DGML**</span><span class="sxs-lookup"><span data-stu-id="27925-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-individual-components-tab"></a><span data-ttu-id="27925-115">Установка с использованием вкладки "Отдельные компоненты"</span><span class="sxs-lookup"><span data-stu-id="27925-115">Install using the Individual components tab</span></span>

1. <span data-ttu-id="27925-116">Запустите **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="27925-116">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="27925-117">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="27925-117">Select **Modify**</span></span> 
1. <span data-ttu-id="27925-118">Откройте вкладку **Отдельные компоненты**.</span><span class="sxs-lookup"><span data-stu-id="27925-118">Select the **Individual components** tab</span></span> 
1. <span data-ttu-id="27925-119">Установите флажок **SDK-пакет .NET Compiler Platform**.</span><span class="sxs-lookup"><span data-stu-id="27925-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="27925-120">Нужный пакет будет представлен в разделе **Компиляторы, средства сборки и среды выполнения** в самом начале.</span><span class="sxs-lookup"><span data-stu-id="27925-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="27925-121">Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:</span><span class="sxs-lookup"><span data-stu-id="27925-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="27925-122">Установите флажок **Редактор DGML**.</span><span class="sxs-lookup"><span data-stu-id="27925-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="27925-123">Нужный пакет будет представлен в разделе **Средства для работы с кодом**.</span><span class="sxs-lookup"><span data-stu-id="27925-123">You'll find it under the **Code tools** section.</span></span>
