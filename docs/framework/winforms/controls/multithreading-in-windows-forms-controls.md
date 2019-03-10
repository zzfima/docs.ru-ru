---
title: Многопоточность в элементах управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703326"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="5a77d-102">Многопоточность в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a77d-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="5a77d-103">Во многих приложениях можно сделать более быстро реагирующих пользовательский интерфейс (UI), выполнять длительные операции в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="5a77d-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="5a77d-104">Несколько средств, доступных для многопоточности элементов управления Windows Forms, включая <xref:System.Threading> пространства имен, <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> метод и `BackgroundWorker` компонента.</span><span class="sxs-lookup"><span data-stu-id="5a77d-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a77d-105">`BackgroundWorker` Компонент заменяет и расширяет его функциональные возможности <xref:System.Threading> пространства имен и <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> метода; тем не менее, их можно сохранить для обратной совместимости и использования в будущем, при выборе.</span><span class="sxs-lookup"><span data-stu-id="5a77d-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="5a77d-106">Дополнительные сведения см. в разделе [Общие сведения о компоненте BackgroundWorker](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5a77d-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a77d-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5a77d-107">In This Section</span></span>  
 [<span data-ttu-id="5a77d-108">Практическое руководство. Сделать потокобезопасных вызовов элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a77d-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="5a77d-109">Демонстрирует процесс создания потокобезопасных вызовов элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5a77d-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="5a77d-110">Практическое руководство. Используйте фоновый поток для поиска файлов</span><span class="sxs-lookup"><span data-stu-id="5a77d-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="5a77d-111">Демонстрируется использование <xref:System.Threading> пространства имен и <xref:System.Windows.Forms.Control.BeginInvoke%2A> метод для поиска файлов асинхронно.</span><span class="sxs-lookup"><span data-stu-id="5a77d-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5a77d-112">Ссылка</span><span class="sxs-lookup"><span data-stu-id="5a77d-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="5a77d-113">Описание компонента, инкапсулирующего рабочий поток для асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="5a77d-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="5a77d-114">Описание способа загрузки звука асинхронно.</span><span class="sxs-lookup"><span data-stu-id="5a77d-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="5a77d-115">Описание способа асинхронной загрузки изображения.</span><span class="sxs-lookup"><span data-stu-id="5a77d-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5a77d-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5a77d-116">Related Sections</span></span>  
 [<span data-ttu-id="5a77d-117">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="5a77d-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="5a77d-118">Как выполнять длительную операцию с <xref:System.ComponentModel.BackgroundWorker> компонента.</span><span class="sxs-lookup"><span data-stu-id="5a77d-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="5a77d-119">Общие сведения о компоненте BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="5a77d-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="5a77d-120">Разделы, описывающие способы использования <xref:System.ComponentModel.BackgroundWorker> компонент для асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="5a77d-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
