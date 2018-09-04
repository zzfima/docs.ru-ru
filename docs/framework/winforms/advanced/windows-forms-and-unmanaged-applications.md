---
title: Windows Forms и неуправляемые приложения
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: bc0c848d1c92871dacab93497c674645f3ac83fe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560326"
---
# <a name="windows-forms-and-unmanaged-applications"></a><span data-ttu-id="9475f-102">Windows Forms и неуправляемые приложения</span><span class="sxs-lookup"><span data-stu-id="9475f-102">Windows Forms and Unmanaged Applications</span></span>
<span data-ttu-id="9475f-103">Приложения и элементы управления Windows Forms могут взаимодействовать с неуправляемыми приложениями, но с некоторыми оговорками.</span><span class="sxs-lookup"><span data-stu-id="9475f-103">Windows Forms applications and controls can interoperate with unmanaged applications, with some caveats.</span></span> <span data-ttu-id="9475f-104">В следующих разделах описываются сценарии и конфигурации, которые поддерживаются и не поддерживаются элементами управления и приложениями Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9475f-104">The following sections describe the scenarios and configurations that Windows Forms applications and controls support and those that they do not support.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9475f-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9475f-105">In This Section</span></span>  
 [<span data-ttu-id="9475f-106">Общие сведения о Windows Forms и неуправляемых приложениях</span><span class="sxs-lookup"><span data-stu-id="9475f-106">Windows Forms and Unmanaged Applications Overview</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 <span data-ttu-id="9475f-107">Общие сведения о том, как использовать и реализовывать элементы управления Windows Forms, которые работают с неуправляемыми приложениями.</span><span class="sxs-lookup"><span data-stu-id="9475f-107">Offers general information about how to use and implement Windows Forms controls that work with unmanaged applications.</span></span>  
  
 [<span data-ttu-id="9475f-108">Практическое руководство. Поддержка COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog</span><span class="sxs-lookup"><span data-stu-id="9475f-108">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 <span data-ttu-id="9475f-109">Пример кода, который демонстрирует использование метода <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> для запуска формы Windows Forms в неуправляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="9475f-109">Provides a code example that shows how to use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to run a Windows Form in an unmanaged application.</span></span>  
  
 [<span data-ttu-id="9475f-110">Практическое руководство. Поддержка COM-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке</span><span class="sxs-lookup"><span data-stu-id="9475f-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 <span data-ttu-id="9475f-111">Пример кода, демонстрирующий выполнение формы Windows Forms в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="9475f-111">Provides a code example that shows how to run a Windows Form on its own thread.</span></span>  
  
 <span data-ttu-id="9475f-112">Также см. в разделе [Пошаговое руководство: поддержка COM-взаимодействия путем отображения каждой формы Windows, в отдельном потоке](https://msdn.microsoft.com/library/ms233639\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9475f-112">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](https://msdn.microsoft.com/library/ms233639\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9475f-113">Ссылка</span><span class="sxs-lookup"><span data-stu-id="9475f-113">Reference</span></span>  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 <span data-ttu-id="9475f-114">Используется для создания отдельного потока для формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9475f-114">Used to create a separate thread for a Windows Form.</span></span>  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 <span data-ttu-id="9475f-115">Запускает цикл сообщений для потока.</span><span class="sxs-lookup"><span data-stu-id="9475f-115">Starts a message loop for a thread.</span></span>  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 <span data-ttu-id="9475f-116">Выполняет маршалинг вызовов из неуправляемого приложения в форму.</span><span class="sxs-lookup"><span data-stu-id="9475f-116">Marshals calls from an unmanaged application to a form.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9475f-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9475f-117">Related Sections</span></span>  
 [<span data-ttu-id="9475f-118">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="9475f-118">Exposing .NET Framework Components to COM</span></span>](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="9475f-119">Общие сведения об использовании типов .NET Framework в неуправляемых приложениях.</span><span class="sxs-lookup"><span data-stu-id="9475f-119">Offers general information about how to use .NET Framework types in unmanaged applications.</span></span>
