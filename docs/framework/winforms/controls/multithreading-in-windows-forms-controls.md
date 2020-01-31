---
title: Многопоточность в элементах управления
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742139"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="c555b-102">Многопоточность в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c555b-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="c555b-103">Во многих приложениях можно сделать пользовательский интерфейс более быстрым, выполняя длительные операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="c555b-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="c555b-104">Для многопоточности можно использовать ряд средств для управления Windows Forms, включая пространство имен <xref:System.Threading>, метод <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> и компонент `BackgroundWorker`.</span><span class="sxs-lookup"><span data-stu-id="c555b-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c555b-105">Компонент `BackgroundWorker` заменяет и добавляет функции в пространство имен <xref:System.Threading> и метод <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>. Однако они сохраняются для обратной совместимости и использования в будущем, если вы решили.</span><span class="sxs-lookup"><span data-stu-id="c555b-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="c555b-106">Дополнительные сведения см. в разделе [Общие сведения о компоненте BackgroundWorker](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c555b-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c555b-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c555b-107">In This Section</span></span>  
 [<span data-ttu-id="c555b-108">Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c555b-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="c555b-109">Показывает, как выполнять потокобезопасные вызовы элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c555b-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="c555b-110">Практическое руководство. Применение фонового потока для поиска файлов</span><span class="sxs-lookup"><span data-stu-id="c555b-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="c555b-111">Показывает, как использовать пространство имен <xref:System.Threading> и метод <xref:System.Windows.Forms.Control.BeginInvoke%2A> для асинхронного поиска файлов.</span><span class="sxs-lookup"><span data-stu-id="c555b-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c555b-112">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="c555b-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="c555b-113">Документирует компонент, инкапсулирующий рабочий поток для асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="c555b-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="c555b-114">Документация по асинхронной загрузке звука.</span><span class="sxs-lookup"><span data-stu-id="c555b-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="c555b-115">Документация по асинхронной загрузке изображения.</span><span class="sxs-lookup"><span data-stu-id="c555b-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c555b-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c555b-116">Related Sections</span></span>  
 [<span data-ttu-id="c555b-117">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="c555b-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="c555b-118">Показывает, как выполнить трудоемкую операцию с компонентом <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="c555b-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="c555b-119">Общие сведения о компоненте BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="c555b-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="c555b-120">Содержит разделы, в которых описывается использование компонента <xref:System.ComponentModel.BackgroundWorker> для асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="c555b-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
