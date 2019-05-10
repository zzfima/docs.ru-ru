---
title: Практическое руководство. Поддержка COM-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
ms.openlocfilehash: 56eaf438455754c69b2df3ff798cf6d2ac6f7549
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64636970"
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a><span data-ttu-id="66918-102">Практическое руководство. Поддержка COM-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке</span><span class="sxs-lookup"><span data-stu-id="66918-102">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>
<span data-ttu-id="66918-103">Проблемы COM-взаимодействия можно устранить путем отображения формы в цикле обработки сообщений [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , который можно создать с помощью метода <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="66918-103">You can resolve COM interoperability problems by displaying your form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop, which you can create by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="66918-104">Чтобы исправить работу формы Windows Forms из клиентского приложения COM, необходимо запустить форму в цикле обработки сообщений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="66918-104">To make a Windows Form work correctly from a COM client application, you must run the form on a Windows Forms message loop.</span></span> <span data-ttu-id="66918-105">Для этого воспользуйтесь одним из перечисленных ниже подходов.</span><span class="sxs-lookup"><span data-stu-id="66918-105">To do this, use one of the following approaches:</span></span>  
  
- <span data-ttu-id="66918-106">Используйте метод <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> для отображения Windows Form.</span><span class="sxs-lookup"><span data-stu-id="66918-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form.</span></span> <span data-ttu-id="66918-107">Дополнительные сведения см. в разделе [Как Поддержка COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog](com-interop-by-displaying-a-windows-form-shadow.md).</span><span class="sxs-lookup"><span data-stu-id="66918-107">For more information, see [How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method](com-interop-by-displaying-a-windows-form-shadow.md).</span></span>  
  
- <span data-ttu-id="66918-108">Отображайте каждую форму Windows Forms в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="66918-108">Display each Windows Form on a separate thread.</span></span>  
  
 <span data-ttu-id="66918-109">Имеется широкая поддержка этой возможности в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66918-109">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="66918-110">Также см. в разделе [Пошаговое руководство: Поддержка COM-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="66918-110">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66918-111">Пример</span><span class="sxs-lookup"><span data-stu-id="66918-111">Example</span></span>  
 <span data-ttu-id="66918-112">В следующем примере кода демонстрируется отображение формы в отдельном потоке и вызов метода <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> для запуска загрузки сообщений Windows Forms в этом потоке.</span><span class="sxs-lookup"><span data-stu-id="66918-112">The following code example demonstrates how to display the form on a separate thread and call the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method to start a Windows Forms message pump on that thread.</span></span> <span data-ttu-id="66918-113">Чтобы использовать этот подход, необходимо выполнять маршалинг всех обращений к форме из приложения неуправляемого кода с помощью метода <xref:System.Windows.Forms.Control.Invoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="66918-113">To use this approach, you must marshal any calls to the form from the unmanaged application by using the <xref:System.Windows.Forms.Control.Invoke%2A> method.</span></span>  
  
 <span data-ttu-id="66918-114">Этот подход требует, что каждый экземпляр формы выполнялся в своем собственном потоке с использованием собственного цикла обработки сообщений.</span><span class="sxs-lookup"><span data-stu-id="66918-114">This approach requires that each instance of a form runs on its own thread by using its own message loop.</span></span> <span data-ttu-id="66918-115">В каждом потоке не может быть более одного цикла обработки сообщений.</span><span class="sxs-lookup"><span data-stu-id="66918-115">You cannot have more than one message loop running per thread.</span></span> <span data-ttu-id="66918-116">Таким образом, изменить цикл обработки сообщений клиентского приложения нельзя.</span><span class="sxs-lookup"><span data-stu-id="66918-116">Therefore, you cannot change the client application's message loop.</span></span> <span data-ttu-id="66918-117">Однако можно изменить компонент [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для запуска нового потока, использующего собственный цикл обработки сообщений.</span><span class="sxs-lookup"><span data-stu-id="66918-117">However, you can modify the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] component to start a new thread that uses its own message loop.</span></span>  
  
 [!code-vb[System.Windows.Forms.ComInterop#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="66918-118">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="66918-118">Compiling the Code</span></span>  
  
- <span data-ttu-id="66918-119">Скомпилируйте типы `COMForm`, `Form1`и `FormManager` в сборку и назовите ее `COMWinform.dll`.</span><span class="sxs-lookup"><span data-stu-id="66918-119">Compile the `COMForm`, `Form1`, and `FormManager` types into an assembly called `COMWinform.dll`.</span></span> <span data-ttu-id="66918-120">Зарегистрируйте сборку для COM-взаимодействия с помощью одного из методов, описанных в разделе [Packaging an Assembly for COM](../../interop/packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="66918-120">Register the assembly for COM interop by using one of the methods described in [Packaging an Assembly for COM](../../interop/packaging-an-assembly-for-com.md).</span></span> <span data-ttu-id="66918-121">Теперь можно использовать сборку и соответствующий ей файл библиотеки типов (с расширением TLB) в неуправляемых приложениях.</span><span class="sxs-lookup"><span data-stu-id="66918-121">You can now use the assembly and its corresponding type library (.tlb) file in unmanaged applications.</span></span> <span data-ttu-id="66918-122">Например, можно использовать библиотеку типов как ссылку в проекте исполняемого файла Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="66918-122">For example, you can use the type library as a reference in a Visual Basic 6.0 executable project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66918-123">См. также</span><span class="sxs-lookup"><span data-stu-id="66918-123">See also</span></span>

- [<span data-ttu-id="66918-124">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="66918-124">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="66918-125">Упаковка сборки для модели COM</span><span class="sxs-lookup"><span data-stu-id="66918-125">Packaging an Assembly for COM</span></span>](../../interop/packaging-an-assembly-for-com.md)
- [<span data-ttu-id="66918-126">Регистрация сборок в COM</span><span class="sxs-lookup"><span data-stu-id="66918-126">Registering Assemblies with COM</span></span>](../../interop/registering-assemblies-with-com.md)
- [<span data-ttu-id="66918-127">Практическое руководство. Поддержка COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog</span><span class="sxs-lookup"><span data-stu-id="66918-127">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](com-interop-by-displaying-a-windows-form-shadow.md)
- [<span data-ttu-id="66918-128">Общие сведения о Windows Forms и неуправляемых приложениях</span><span class="sxs-lookup"><span data-stu-id="66918-128">Windows Forms and Unmanaged Applications Overview</span></span>](windows-forms-and-unmanaged-applications-overview.md)
