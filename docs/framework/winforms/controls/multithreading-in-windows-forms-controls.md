---
title: "Многопоточность в элементах управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c4651ca9707dcf0fac2edea0f004275cfcf18cf2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="2db22-102">Многопоточность в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2db22-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="2db22-103">Во многих приложениях можно сделать более быстрого реагирования пользовательского интерфейса (UI), выполнять длительные операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="2db22-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="2db22-104">Доступно несколько средств для многопоточности элементов управления Windows Forms, включая <xref:System.Threading> пространства имен, <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> метода и `BackgroundWorker` компонента.</span><span class="sxs-lookup"><span data-stu-id="2db22-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2db22-105">`BackgroundWorker` Компонент заменяет и расширяет его функциональные возможности <xref:System.Threading> пространства имен и <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> метода; тем не менее, их можно сохранить для обратной совместимости и использования в будущем, при выборе.</span><span class="sxs-lookup"><span data-stu-id="2db22-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="2db22-106">Дополнительные сведения см. в разделе [Общие сведения о компоненте BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2db22-106">For more information, see [BackgroundWorker Component Overview](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2db22-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="2db22-107">In This Section</span></span>  
 [<span data-ttu-id="2db22-108">Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2db22-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="2db22-109">Описание способов обеспечения потокобезопасных вызовов элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2db22-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="2db22-110">Практическое руководство. Применение фонового потока для поиска файлов</span><span class="sxs-lookup"><span data-stu-id="2db22-110">How to: Use a Background Thread to Search for Files</span></span>](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="2db22-111">Показано, как использовать <xref:System.Threading> пространства имен и <xref:System.Windows.Forms.Control.BeginInvoke%2A> метод для поиска файлов асинхронно.</span><span class="sxs-lookup"><span data-stu-id="2db22-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2db22-112">Ссылка</span><span class="sxs-lookup"><span data-stu-id="2db22-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="2db22-113">Описание компонента, инкапсулирующего рабочий поток для асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="2db22-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="2db22-114">Описание способа асинхронной загрузки звука.</span><span class="sxs-lookup"><span data-stu-id="2db22-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="2db22-115">Описание способа асинхронной загрузки изображения.</span><span class="sxs-lookup"><span data-stu-id="2db22-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2db22-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2db22-116">Related Sections</span></span>  
 [<span data-ttu-id="2db22-117">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="2db22-117">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="2db22-118">Описание способов выполнения длительной операции с <xref:System.ComponentModel.BackgroundWorker> компонента.</span><span class="sxs-lookup"><span data-stu-id="2db22-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="2db22-119">Общие сведения о компоненте BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="2db22-119">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="2db22-120">Разделы, описывающие способы использования <xref:System.ComponentModel.BackgroundWorker> компонента для асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="2db22-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
