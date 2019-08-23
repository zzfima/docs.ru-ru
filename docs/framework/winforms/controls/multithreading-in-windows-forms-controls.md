---
title: Многопоточность в элементах управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cf6790172b7445ad154eead5d17f8efddd78ffee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952682"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="d95d6-102">Многопоточность в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d95d6-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="d95d6-103">Во многих приложениях можно сделать пользовательский интерфейс более быстрым, выполняя длительные операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="d95d6-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="d95d6-104">Существует ряд средств для многопоточности элементов управления Windows Forms, включая <xref:System.Threading> пространство имен <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> , метод и `BackgroundWorker` компонент.</span><span class="sxs-lookup"><span data-stu-id="d95d6-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d95d6-105">Компонент заменяет и добавляет функции <xref:System.Threading> к пространству имен и <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> методу. Однако они сохраняются для обратной совместимости и использования в будущем, если вы решили. `BackgroundWorker`</span><span class="sxs-lookup"><span data-stu-id="d95d6-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="d95d6-106">Дополнительные сведения см. в разделе [Общие сведения о компоненте BackgroundWorker](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d95d6-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d95d6-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d95d6-107">In This Section</span></span>  
 [<span data-ttu-id="d95d6-108">Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d95d6-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="d95d6-109">Показывает, как выполнять потокобезопасные вызовы элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d95d6-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="d95d6-110">Практическое руководство. Использовать фоновый поток для поиска файлов</span><span class="sxs-lookup"><span data-stu-id="d95d6-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="d95d6-111">Показывает, как использовать <xref:System.Threading> пространство имен <xref:System.Windows.Forms.Control.BeginInvoke%2A> и метод для асинхронного поиска файлов.</span><span class="sxs-lookup"><span data-stu-id="d95d6-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d95d6-112">Ссылка</span><span class="sxs-lookup"><span data-stu-id="d95d6-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="d95d6-113">Документирует компонент, инкапсулирующий рабочий поток для асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="d95d6-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="d95d6-114">Документация по асинхронной загрузке звука.</span><span class="sxs-lookup"><span data-stu-id="d95d6-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="d95d6-115">Документация по асинхронной загрузке изображения.</span><span class="sxs-lookup"><span data-stu-id="d95d6-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d95d6-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d95d6-116">Related Sections</span></span>  
 [<span data-ttu-id="d95d6-117">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="d95d6-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="d95d6-118">Показывает, как выполнить трудоемкую операцию с <xref:System.ComponentModel.BackgroundWorker> компонентом.</span><span class="sxs-lookup"><span data-stu-id="d95d6-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="d95d6-119">Общие сведения о компоненте BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="d95d6-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="d95d6-120">Содержит разделы, в которых описывается использование <xref:System.ComponentModel.BackgroundWorker> компонента для асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="d95d6-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
