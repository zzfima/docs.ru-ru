---
title: "Выбор .NET Framework 2.0 в качестве целевой платформы в Windows 8"
description: "Дополнительные сведения о назначении старой версии платформы .NET, при использовании F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63989543-95c3-4ab7-81f3-3834a8b15010
ms.openlocfilehash: 2c0191267da5bee7b844c11cdee168ccfb3321c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="targeting-older-versions-of-net"></a><span data-ttu-id="d94f2-104">Нацеливание на предыдущие версии .NET</span><span class="sxs-lookup"><span data-stu-id="d94f2-104">Targeting Older Versions of .NET</span></span>

> [!NOTE]
<span data-ttu-id="d94f2-105">Данная статья не в курсе последних Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d94f2-105">This article is not up to date with the latest Visual Studio.</span></span>  <span data-ttu-id="d94f2-106">Он будет обновляться.</span><span class="sxs-lookup"><span data-stu-id="d94f2-106">It will be updated.</span></span>

<span data-ttu-id="d94f2-107">Может возникнуть следующая ошибка при попытке платформы .NET Framework 2.0, 3.0 или 3.5 в языке F # проекта во время установки Visual Studio на Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="d94f2-107">The following error might appear if you try to target the .NET Framework 2.0, 3.0, or 3.5 in an F# project when Visual Studio is installed on Windows 8.1:</span></span> 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

<span data-ttu-id="d94f2-108">Эта ошибка известно, что происходит при следующем сочетании условий:</span><span class="sxs-lookup"><span data-stu-id="d94f2-108">This error is known to occur under the following combination of conditions:</span></span>


- <span data-ttu-id="d94f2-109">Вы установили Visual Studio на Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="d94f2-109">You installed Visual Studio on Windows 8.1.</span></span>
<br />

- <span data-ttu-id="d94f2-110">Не удалось включить .NET Framework 3.5 перед установкой Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d94f2-110">You didn’t enable the .NET Framework 3.5 before you installed Visual Studio.</span></span>
<br />

- <span data-ttu-id="d94f2-111">Проект предназначен для .NET Framework 2.0, 3.0 или 3.5.</span><span class="sxs-lookup"><span data-stu-id="d94f2-111">Your project targets the .NET Framework 2.0, 3.0, or 3.5.</span></span>
<br />

<span data-ttu-id="d94f2-112">При установке Visual Studio, он обнаруживает установленные версии платформы .NET Framework и устанавливает F # 2.0 Runtime только в том случае, если установлен и включен на .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="d94f2-112">When you install Visual Studio, it detects the installed versions of the .NET Framework and installs the F# 2.0 Runtime only if the .NET Framework 3.5 is installed and enabled.</span></span>


## <a name="resolving-the-error"></a><span data-ttu-id="d94f2-113">Устранение ошибок</span><span class="sxs-lookup"><span data-stu-id="d94f2-113">Resolving the Error</span></span>
<span data-ttu-id="d94f2-114">Чтобы устранить эту ошибку, можно либо целевой более новой версии платформы .NET Framework, либо можно включить .NET Framework 3.5 в Windows 8.1 и установить среду выполнения F # 2.0, запустив программу установки для Visual Studio с **восстановления** параметр.</span><span class="sxs-lookup"><span data-stu-id="d94f2-114">To resolve this error, you can either target a newer version of the .NET Framework, or you can enable the .NET Framework 3.5 on Windows 8.1 and then install the F# 2.0 runtime by running the setup program for Visual Studio with the **Repair** option.</span></span>


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a><span data-ttu-id="d94f2-115">Чтобы включить .NET Framework 3.5 в Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d94f2-115">To enable the .NET Framework 3.5 on Windows 8.1</span></span>

1. <span data-ttu-id="d94f2-116">На **запустить** экрана, начать ввод **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="d94f2-116">On the **Start** screen, start to enter **Control Panel**.</span></span>
<br />  <span data-ttu-id="d94f2-117">При вводе этого имени **панели управления** отображается значок **приложений** заголовок.</span><span class="sxs-lookup"><span data-stu-id="d94f2-117">As you enter that name, the **Control Panel** icon appears under the **Apps** heading.</span></span>
<br />

2. <span data-ttu-id="d94f2-118">Выберите **панели управления** значок, выберите **программы** значок и выберите **Включение или отключение компонентов** ссылку.</span><span class="sxs-lookup"><span data-stu-id="d94f2-118">Choose the **Control Panel** icon, choose the **Programs** icon, and then choose the **Turn Windows features on or off** link.</span></span>
<br />

3. <span data-ttu-id="d94f2-119">Убедитесь, что **.NET Framework 3.5 (включает .NET 2.0 и 3.0)** флажок установлен, а затем выберите **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="d94f2-119">Make sure that the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box is selected, and then choose the **OK** button.</span></span>
<br />  <span data-ttu-id="d94f2-120">Установите флажки для всех дочерних узлов для дополнительных компонентов платформы .NET Framework не требуется.</span><span class="sxs-lookup"><span data-stu-id="d94f2-120">You don’t need to select the check boxes for any child nodes for optional components of the .NET Framework.</span></span>
<br />  <span data-ttu-id="d94f2-121">.NET Framework 3.5 доступен в том случае, если он еще не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="d94f2-121">The .NET Framework 3.5 is enabled if it wasn't already.</span></span>
<br />


#### <a name="to-install-the-f-20-runtime"></a><span data-ttu-id="d94f2-122">Чтобы установить среду выполнения F # 2.0</span><span class="sxs-lookup"><span data-stu-id="d94f2-122">To install the F# 2.0 runtime</span></span>

1. <span data-ttu-id="d94f2-123">В панели управления выберите **программы** связь, а затем выберите **программы и компоненты** ссылку.</span><span class="sxs-lookup"><span data-stu-id="d94f2-123">In the Control Panel, choose the **Programs** link, and then choose the **Programs and Features** link.</span></span>
<br />

2. <span data-ttu-id="d94f2-124">В списке установленных программ выберите выпуск Visual Studio, установлен, а затем выберите **изменений** кнопки.</span><span class="sxs-lookup"><span data-stu-id="d94f2-124">In the list of installed programs, choose the edition of Visual Studio that you installed, and then choose the **Change** button.</span></span>
<br />

3. <span data-ttu-id="d94f2-125">После запуска программы установки, выберите **восстановления** кнопки.</span><span class="sxs-lookup"><span data-stu-id="d94f2-125">After setup starts, choose the **Repair** button.</span></span>
<br />  <span data-ttu-id="d94f2-126">Дополнительные сведения см. в разделе [установка Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span><span class="sxs-lookup"><span data-stu-id="d94f2-126">For more information, see [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span></span>
<br />
## <a name="see-also"></a><span data-ttu-id="d94f2-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d94f2-127">See Also</span></span>
[<span data-ttu-id="d94f2-128">Visual F#</span><span class="sxs-lookup"><span data-stu-id="d94f2-128">Visual F#</span></span>](../index.md)
