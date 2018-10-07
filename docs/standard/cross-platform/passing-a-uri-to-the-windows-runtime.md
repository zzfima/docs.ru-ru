---
title: Передача URI в среду выполнения Windows
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f019c1075c119c3d814b3b7add8fe30f3e4d107
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48844557"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="1398b-102">Передача URI в среду выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="1398b-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="1398b-103">Методы среды выполнения Windows принимают только абсолютные URI.</span><span class="sxs-lookup"><span data-stu-id="1398b-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="1398b-104">Если передать относительный URI методу [!INCLUDE[wrt](../../../includes/wrt-md.md)], вызывается исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="1398b-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="1398b-105">Вот почему: при использовании [!INCLUDE[wrt](../../../includes/wrt-md.md)] в коде .NET Framework, <xref:Windows.Foundation.Uri?displayProperty=nameWithType> класс отображается как <xref:System.Uri?displayProperty=nameWithType> в Intellisense.</span><span class="sxs-lookup"><span data-stu-id="1398b-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="1398b-106"><xref:System.Uri?displayProperty=nameWithType> Класс допускает относительные URI, но <xref:Windows.Foundation.Uri?displayProperty=nameWithType> класс — нет.</span><span class="sxs-lookup"><span data-stu-id="1398b-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="1398b-107">Это также справедливо для методов, доступных в компонентах [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1398b-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="1398b-108">Если компонент предоставляет метод, принимающий URI, сигнатура в коде содержит <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1398b-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1398b-109">Тем не менее, для пользователей вашего компонента сигнатура содержит <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1398b-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1398b-110">URI, переданный вашему компоненту, должен быть абсолютным.</span><span class="sxs-lookup"><span data-stu-id="1398b-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
 <span data-ttu-id="1398b-111">В этом разделе показано, как определить абсолютный URI и как создать его при указании ссылки на ресурс в пакете приложения.</span><span class="sxs-lookup"><span data-stu-id="1398b-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="1398b-112">Определение и использование абсолютного URI</span><span class="sxs-lookup"><span data-stu-id="1398b-112">Detecting and using an absolute URI</span></span>  
 <span data-ttu-id="1398b-113">Используйте свойство <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>, чтобы убедиться, что URI является абсолютным, перед его передачей классу [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1398b-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="1398b-114">Такой подход более эффективен, чем перехват и обработка исключения <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="1398b-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="1398b-115">Использование абсолютного URI для ресурса в пакете приложения</span><span class="sxs-lookup"><span data-stu-id="1398b-115">Using an absolute URI for a resource in the app package</span></span>  
 <span data-ttu-id="1398b-116">Чтобы указать URI для ресурса в пакете приложения, можно использовать схему `ms-appx` или `ms-appx-web` для создания абсолютного URI.</span><span class="sxs-lookup"><span data-stu-id="1398b-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
 <span data-ttu-id="1398b-117">В следующем примере показано, как задать [источника](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) свойство для [WebView](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) управления и [источника](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) свойство для [образа](https://msdn.microsoft.com/library/windows/apps/br242752.aspx) управления к ресурсам, которые содержатся в папке с именем страниц с помощью XAML и кода.</span><span class="sxs-lookup"><span data-stu-id="1398b-117">The following example shows how to set the [Source](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) property for a [WebView](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) control and the [Source](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) property for an [Image](https://msdn.microsoft.com/library/windows/apps/br242752.aspx) control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 <span data-ttu-id="1398b-118">Дополнительные сведения об этих схемах см. в разделе [схем URI](https://msdn.microsoft.com/library/windows/apps/jj655406.aspx) в центре разработки для Windows.</span><span class="sxs-lookup"><span data-stu-id="1398b-118">For more information about these schemes, see [URI schemes](https://msdn.microsoft.com/library/windows/apps/jj655406.aspx) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1398b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1398b-119">See also</span></span>

- [<span data-ttu-id="1398b-120">Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="1398b-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
