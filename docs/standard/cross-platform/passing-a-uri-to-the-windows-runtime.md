---
title: "Передача URI в среду выполнения Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4ef77fb9e196abf046e0d4648a49b5d4d3fad47e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="eac83-102">Передача URI в среду выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="eac83-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="eac83-103">Методы среды выполнения Windows принимают только абсолютные URI.</span><span class="sxs-lookup"><span data-stu-id="eac83-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="eac83-104">Если передать относительный URI методу [!INCLUDE[wrt](../../../includes/wrt-md.md)], вызывается исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="eac83-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="eac83-105">Вот почему: при использовании [!INCLUDE[wrt](../../../includes/wrt-md.md)] в коде .NET Framework [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) класс отображается как <xref:System.Uri?displayProperty=nameWithType> в Intellisense.</span><span class="sxs-lookup"><span data-stu-id="eac83-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="eac83-106"><xref:System.Uri?displayProperty=nameWithType> Класс допускает относительные URI, но [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) класса — нет.</span><span class="sxs-lookup"><span data-stu-id="eac83-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) class does not.</span></span> <span data-ttu-id="eac83-107">Это также справедливо для методов, доступных в компонентах [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eac83-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="eac83-108">Если компонент предоставляет метод, принимающий URI, сигнатура в коде содержит <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eac83-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eac83-109">Однако для пользователей вашего компонента сигнатура содержит [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376).</span><span class="sxs-lookup"><span data-stu-id="eac83-109">However, to users of your component, the signature includes [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376).</span></span> <span data-ttu-id="eac83-110">URI, переданный вашему компоненту, должен быть абсолютным.</span><span class="sxs-lookup"><span data-stu-id="eac83-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
 <span data-ttu-id="eac83-111">В этом разделе показано, как определить абсолютный URI и как создать его при указании ссылки на ресурс в пакете приложения.</span><span class="sxs-lookup"><span data-stu-id="eac83-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="eac83-112">Определение и использование абсолютного URI</span><span class="sxs-lookup"><span data-stu-id="eac83-112">Detecting and using an absolute URI</span></span>  
 <span data-ttu-id="eac83-113">Используйте свойство <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>, чтобы убедиться, что URI является абсолютным, перед его передачей классу [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eac83-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="eac83-114">Такой подход более эффективен, чем перехват и обработка исключения <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="eac83-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="eac83-115">Использование абсолютного URI для ресурса в пакете приложения</span><span class="sxs-lookup"><span data-stu-id="eac83-115">Using an absolute URI for a resource in the app package</span></span>  
 <span data-ttu-id="eac83-116">Чтобы указать URI для ресурса в пакете приложения, можно использовать схему `ms-appx` или `ms-appx-web` для создания абсолютного URI.</span><span class="sxs-lookup"><span data-stu-id="eac83-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
 <span data-ttu-id="eac83-117">Следующий пример показывает, как задать [источника](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) свойство для [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) управления и [источника](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) свойство [изображения](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) управления для ресурсов, содержащихся в папке страниц с использованием XAML и кода.</span><span class="sxs-lookup"><span data-stu-id="eac83-117">The following example shows how to set the [Source](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) property for a [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) control and the [Source](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) property for an [Image](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 <span data-ttu-id="eac83-118">Дополнительные сведения об этих схемах см. в разделе [схемы URI](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) в центре разработчиков Windows.</span><span class="sxs-lookup"><span data-stu-id="eac83-118">For more information about these schemes, see [URI schemes](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac83-119">См. также</span><span class="sxs-lookup"><span data-stu-id="eac83-119">See Also</span></span>  
 [<span data-ttu-id="eac83-120">Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="eac83-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
