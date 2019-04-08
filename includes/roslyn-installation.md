---
ms.openlocfilehash: 72acd0029d0189de1c724856572957f111b9d18f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760395"
---
## <a name="installation-instructions"></a><span data-ttu-id="60d74-101">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="60d74-101">Installation instructions</span></span> 

<span data-ttu-id="60d74-102">Найти **SDK-пакет .NET Compiler Platform** в **Visual Studio Installer** можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="60d74-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-workloads-view"></a><span data-ttu-id="60d74-103">Установка с помощью представления рабочих нагрузок</span><span class="sxs-lookup"><span data-stu-id="60d74-103">Install using the Workloads view</span></span>

<span data-ttu-id="60d74-104">SDK-пакет .NET Compiler Platform не выбирается автоматически в рамках рабочей нагрузки разработки расширений Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="60d74-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="60d74-105">Его необходимо выбрать как дополнительный компонент.</span><span class="sxs-lookup"><span data-stu-id="60d74-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="60d74-106">Запустите **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="60d74-106">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="60d74-107">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="60d74-107">Select **Modify**</span></span> 
1. <span data-ttu-id="60d74-108">Отметьте рабочую нагрузку **Разработка расширений Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="60d74-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="60d74-109">Откройте узел **Разработка расширений Visual Studio** в дереве сводки.</span><span class="sxs-lookup"><span data-stu-id="60d74-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="60d74-110">Установите флажок **SDK-пакет .NET Compiler Platform**.</span><span class="sxs-lookup"><span data-stu-id="60d74-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="60d74-111">Нужный пакет будет представлен последним в списке дополнительных компонентов.</span><span class="sxs-lookup"><span data-stu-id="60d74-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="60d74-112">Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:</span><span class="sxs-lookup"><span data-stu-id="60d74-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="60d74-113">Откройте узел **Отдельные компоненты** в дереве сводки.</span><span class="sxs-lookup"><span data-stu-id="60d74-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="60d74-114">Установите флажок **Редактор DGML**</span><span class="sxs-lookup"><span data-stu-id="60d74-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-individual-components-tab"></a><span data-ttu-id="60d74-115">Установка с использованием вкладки "Отдельные компоненты"</span><span class="sxs-lookup"><span data-stu-id="60d74-115">Install using the Individual components tab</span></span>

1. <span data-ttu-id="60d74-116">Запустите **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="60d74-116">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="60d74-117">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="60d74-117">Select **Modify**</span></span> 
1. <span data-ttu-id="60d74-118">Откройте вкладку **Отдельные компоненты**.</span><span class="sxs-lookup"><span data-stu-id="60d74-118">Select the **Individual components** tab</span></span> 
1. <span data-ttu-id="60d74-119">Установите флажок **SDK-пакет .NET Compiler Platform**.</span><span class="sxs-lookup"><span data-stu-id="60d74-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="60d74-120">Нужный пакет будет представлен в разделе **Компиляторы, средства сборки и среды выполнения** в самом начале.</span><span class="sxs-lookup"><span data-stu-id="60d74-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="60d74-121">Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:</span><span class="sxs-lookup"><span data-stu-id="60d74-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="60d74-122">Установите флажок **Редактор DGML**.</span><span class="sxs-lookup"><span data-stu-id="60d74-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="60d74-123">Нужный пакет будет представлен в разделе **Средства для работы с кодом**.</span><span class="sxs-lookup"><span data-stu-id="60d74-123">You'll find it under the **Code tools** section.</span></span>
