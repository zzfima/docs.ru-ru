---
title: Практическое руководство. Создание предварительно вычисленных задач
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ce34e609dc9b1e2a5f1822ce27f65be74a636c86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="62ae0-102">Практическое руководство. Создание предварительно вычисленных задач</span><span class="sxs-lookup"><span data-stu-id="62ae0-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="62ae0-103">В этом документе описывается способ использования метода <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> для получения результатов асинхронных операций загрузки, удерживаемых в кэше.</span><span class="sxs-lookup"><span data-stu-id="62ae0-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="62ae0-104">Метод <xref:System.Threading.Tasks.Task.FromResult%2A> возвращает завершенный объект <xref:System.Threading.Tasks.Task%601>, содержащий предоставленное значение как свойство <xref:System.Threading.Tasks.Task%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="62ae0-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="62ae0-105">Этот метод полезен тогда, когда выполняется асинхронная операция, возвращающая объект <xref:System.Threading.Tasks.Task%601>, и результат этого объекта <xref:System.Threading.Tasks.Task%601> уже вычислен.</span><span class="sxs-lookup"><span data-stu-id="62ae0-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62ae0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="62ae0-106">Example</span></span>  
 <span data-ttu-id="62ae0-107">В следующем примере загружаются строки из Интернета.</span><span class="sxs-lookup"><span data-stu-id="62ae0-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="62ae0-108">Здесь определяется метод `DownloadStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="62ae0-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="62ae0-109">Этот метод загружает строки из Интернета асинхронным образом.</span><span class="sxs-lookup"><span data-stu-id="62ae0-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="62ae0-110">В этом примере также используется объект <xref:System.Collections.Concurrent.ConcurrentDictionary%602> для кэширования результатов предыдущих операций.</span><span class="sxs-lookup"><span data-stu-id="62ae0-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="62ae0-111">Если введенный адрес хранится в этом кэше, `DownloadStringAsync` использует метод <xref:System.Threading.Tasks.Task.FromResult%2A> для создания объекта <xref:System.Threading.Tasks.Task%601>, содержащего содержимое этого адреса.</span><span class="sxs-lookup"><span data-stu-id="62ae0-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="62ae0-112">В противном случае `DownloadStringAsync` загружает файл из Интернета и добавляет результат в кэш.</span><span class="sxs-lookup"><span data-stu-id="62ae0-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="62ae0-113">В этом примере вычисляется время, необходимое для загрузки нескольких строк дважды.</span><span class="sxs-lookup"><span data-stu-id="62ae0-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="62ae0-114">Второй набор операций загрузки должен занимать меньше времени, чем первый набор, поскольку результаты хранятся в кэше.</span><span class="sxs-lookup"><span data-stu-id="62ae0-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="62ae0-115">Метод <xref:System.Threading.Tasks.Task.FromResult%2A> позволяет методу `DownloadStringAsync` создавать объекты <xref:System.Threading.Tasks.Task%601>, которые содержат эти предварительно вычисленные результаты.</span><span class="sxs-lookup"><span data-stu-id="62ae0-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="62ae0-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="62ae0-116">Compiling the Code</span></span>  
 <span data-ttu-id="62ae0-117">Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `CachedDownloads.cs` (`CachedDownloads.vb` для Visual Basic), затем выполните в окне командной строки Visual Studio следующую команду.</span><span class="sxs-lookup"><span data-stu-id="62ae0-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `CachedDownloads.cs` (`CachedDownloads.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="62ae0-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="62ae0-118">Visual C#</span></span>  
  
 <span data-ttu-id="62ae0-119">**csc.exe CachedDownloads.cs**</span><span class="sxs-lookup"><span data-stu-id="62ae0-119">**csc.exe CachedDownloads.cs**</span></span>  
  
 <span data-ttu-id="62ae0-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62ae0-120">Visual Basic</span></span>  
  
 <span data-ttu-id="62ae0-121">**vbc.exe CachedDownloads.vb**</span><span class="sxs-lookup"><span data-stu-id="62ae0-121">**vbc.exe CachedDownloads.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="62ae0-122">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="62ae0-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ae0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="62ae0-123">See Also</span></span>  
 [<span data-ttu-id="62ae0-124">Асинхронное программирование на основе задач</span><span class="sxs-lookup"><span data-stu-id="62ae0-124">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
