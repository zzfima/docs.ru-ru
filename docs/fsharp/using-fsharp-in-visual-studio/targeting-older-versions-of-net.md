---
title: Выбор .NET Framework 2.0 в качестве целевой платформы в Windows 8
description: 'Дополнительные сведения о назначении старой версии платформы .NET, при использовании F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 9b08cced63b46778a5081d4de710991a6299fd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="targeting-older-versions-of-net"></a><span data-ttu-id="00168-103">Нацеливание на предыдущие версии .NET</span><span class="sxs-lookup"><span data-stu-id="00168-103">Targeting Older Versions of .NET</span></span>

> [!NOTE]
<span data-ttu-id="00168-104">Данная статья не в курсе последних Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="00168-104">This article is not up to date with the latest Visual Studio.</span></span>  <span data-ttu-id="00168-105">Он будет обновляться.</span><span class="sxs-lookup"><span data-stu-id="00168-105">It will be updated.</span></span>

<span data-ttu-id="00168-106">Может возникнуть следующая ошибка при попытке платформы .NET Framework 2.0, 3.0 или 3.5 в языке F # проекта во время установки Visual Studio на Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="00168-106">The following error might appear if you try to target the .NET Framework 2.0, 3.0, or 3.5 in an F# project when Visual Studio is installed on Windows 8.1:</span></span> 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

<span data-ttu-id="00168-107">Эта ошибка известно, что происходит при следующем сочетании условий:</span><span class="sxs-lookup"><span data-stu-id="00168-107">This error is known to occur under the following combination of conditions:</span></span>


- <span data-ttu-id="00168-108">Вы установили Visual Studio на Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="00168-108">You installed Visual Studio on Windows 8.1.</span></span>
<br />

- <span data-ttu-id="00168-109">Не удалось включить .NET Framework 3.5 перед установкой Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="00168-109">You didn’t enable the .NET Framework 3.5 before you installed Visual Studio.</span></span>
<br />

- <span data-ttu-id="00168-110">Проект предназначен для .NET Framework 2.0, 3.0 или 3.5.</span><span class="sxs-lookup"><span data-stu-id="00168-110">Your project targets the .NET Framework 2.0, 3.0, or 3.5.</span></span>
<br />

<span data-ttu-id="00168-111">При установке Visual Studio, он обнаруживает установленные версии платформы .NET Framework и устанавливает F # 2.0 Runtime только в том случае, если установлен и включен на .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="00168-111">When you install Visual Studio, it detects the installed versions of the .NET Framework and installs the F# 2.0 Runtime only if the .NET Framework 3.5 is installed and enabled.</span></span>


## <a name="resolving-the-error"></a><span data-ttu-id="00168-112">Устранение ошибок</span><span class="sxs-lookup"><span data-stu-id="00168-112">Resolving the Error</span></span>
<span data-ttu-id="00168-113">Чтобы устранить эту ошибку, можно либо целевой более новой версии платформы .NET Framework, либо можно включить .NET Framework 3.5 в Windows 8.1 и установить среду выполнения F # 2.0, запустив программу установки для Visual Studio с **восстановления** параметр.</span><span class="sxs-lookup"><span data-stu-id="00168-113">To resolve this error, you can either target a newer version of the .NET Framework, or you can enable the .NET Framework 3.5 on Windows 8.1 and then install the F# 2.0 runtime by running the setup program for Visual Studio with the **Repair** option.</span></span>


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a><span data-ttu-id="00168-114">Чтобы включить .NET Framework 3.5 в Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="00168-114">To enable the .NET Framework 3.5 on Windows 8.1</span></span>

1. <span data-ttu-id="00168-115">На **запустить** экрана, начать ввод **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="00168-115">On the **Start** screen, start to enter **Control Panel**.</span></span>
<br />  <span data-ttu-id="00168-116">При вводе этого имени **панели управления** отображается значок **приложений** заголовок.</span><span class="sxs-lookup"><span data-stu-id="00168-116">As you enter that name, the **Control Panel** icon appears under the **Apps** heading.</span></span>
<br />

2. <span data-ttu-id="00168-117">Выберите **панели управления** значок, выберите **программы** значок и выберите **Включение или отключение компонентов** ссылку.</span><span class="sxs-lookup"><span data-stu-id="00168-117">Choose the **Control Panel** icon, choose the **Programs** icon, and then choose the **Turn Windows features on or off** link.</span></span>
<br />

3. <span data-ttu-id="00168-118">Убедитесь, что **.NET Framework 3.5 (включает .NET 2.0 и 3.0)** флажок установлен, а затем выберите **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="00168-118">Make sure that the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box is selected, and then choose the **OK** button.</span></span>
<br />  <span data-ttu-id="00168-119">Установите флажки для всех дочерних узлов для дополнительных компонентов платформы .NET Framework не требуется.</span><span class="sxs-lookup"><span data-stu-id="00168-119">You don’t need to select the check boxes for any child nodes for optional components of the .NET Framework.</span></span>
<br />  <span data-ttu-id="00168-120">.NET Framework 3.5 доступен в том случае, если он еще не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="00168-120">The .NET Framework 3.5 is enabled if it wasn't already.</span></span>
<br />


#### <a name="to-install-the-f-20-runtime"></a><span data-ttu-id="00168-121">Чтобы установить среду выполнения F # 2.0</span><span class="sxs-lookup"><span data-stu-id="00168-121">To install the F# 2.0 runtime</span></span>

1. <span data-ttu-id="00168-122">В панели управления выберите **программы** связь, а затем выберите **программы и компоненты** ссылку.</span><span class="sxs-lookup"><span data-stu-id="00168-122">In the Control Panel, choose the **Programs** link, and then choose the **Programs and Features** link.</span></span>
<br />

2. <span data-ttu-id="00168-123">В списке установленных программ выберите выпуск Visual Studio, установлен, а затем выберите **изменений** кнопки.</span><span class="sxs-lookup"><span data-stu-id="00168-123">In the list of installed programs, choose the edition of Visual Studio that you installed, and then choose the **Change** button.</span></span>
<br />

3. <span data-ttu-id="00168-124">После запуска программы установки, выберите **восстановления** кнопки.</span><span class="sxs-lookup"><span data-stu-id="00168-124">After setup starts, choose the **Repair** button.</span></span>
<br />  <span data-ttu-id="00168-125">Дополнительные сведения см. в разделе [установка Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span><span class="sxs-lookup"><span data-stu-id="00168-125">For more information, see [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span></span>
<br />
## <a name="see-also"></a><span data-ttu-id="00168-126">См. также</span><span class="sxs-lookup"><span data-stu-id="00168-126">See Also</span></span>
[<span data-ttu-id="00168-127">Visual F#</span><span class="sxs-lookup"><span data-stu-id="00168-127">Visual F#</span></span>](../index.md)
