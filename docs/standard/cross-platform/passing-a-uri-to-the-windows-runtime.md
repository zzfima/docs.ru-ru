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
ms.openlocfilehash: 71d427c2d602efbd92dc0128b1fada85a987904a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123627"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="b2525-102">Передача URI в среду выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="b2525-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="b2525-103">Методы среды выполнения Windows принимают только абсолютные URI.</span><span class="sxs-lookup"><span data-stu-id="b2525-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="b2525-104">Если в метод среда выполнения Windows передается относительный URI, возникает исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="b2525-104">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="b2525-105">Вот почему: при использовании среда выполнения Windows в .NET Frameworkном коде класс <xref:Windows.Foundation.Uri?displayProperty=nameWithType> отображается как <xref:System.Uri?displayProperty=nameWithType> в IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b2525-105">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="b2525-106">Класс <xref:System.Uri?displayProperty=nameWithType> допускает относительные URI, но класс <xref:Windows.Foundation.Uri?displayProperty=nameWithType> не имеет.</span><span class="sxs-lookup"><span data-stu-id="b2525-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="b2525-107">Это также справедливо для методов, предоставляемых в среда выполнения Windowsных компонентах.</span><span class="sxs-lookup"><span data-stu-id="b2525-107">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="b2525-108">Если компонент предоставляет метод, принимающий URI, сигнатура в коде содержит <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2525-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b2525-109">Однако для пользователей компонента подпись включает <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2525-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b2525-110">URI, переданный вашему компоненту, должен быть абсолютным.</span><span class="sxs-lookup"><span data-stu-id="b2525-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="b2525-111">В этом разделе показано, как определить абсолютный URI и как создать его при указании ссылки на ресурс в пакете приложения.</span><span class="sxs-lookup"><span data-stu-id="b2525-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="b2525-112">Определение и использование абсолютного URI</span><span class="sxs-lookup"><span data-stu-id="b2525-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="b2525-113">Используйте свойство <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>, чтобы убедиться, что URI является абсолютным, прежде чем передать его в среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="b2525-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="b2525-114">Такой подход более эффективен, чем перехват и обработка исключения <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="b2525-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="b2525-115">Использование абсолютного URI для ресурса в пакете приложения</span><span class="sxs-lookup"><span data-stu-id="b2525-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="b2525-116">Чтобы указать URI для ресурса в пакете приложения, можно использовать схему `ms-appx` или `ms-appx-web` для создания абсолютного URI.</span><span class="sxs-lookup"><span data-stu-id="b2525-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="b2525-117">В следующем примере показано, как задать свойство <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> для элемента управления <xref:Windows.UI.Xaml.Controls.WebView> и свойство <xref:Windows.UI.Xaml.Controls.Image.Source%2A> для элемента управления <xref:Windows.UI.Xaml.Controls.Image> для ресурсов, содержащихся в папке Pages, с использованием XAML и кода.</span><span class="sxs-lookup"><span data-stu-id="b2525-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="b2525-118">Дополнительные сведения об этих схемах см. в разделе [схемы URI](/windows/uwp/app-resources/uri-schemes) в центре разработки для Windows.</span><span class="sxs-lookup"><span data-stu-id="b2525-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2525-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b2525-119">See also</span></span>

- [<span data-ttu-id="b2525-120">Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="b2525-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
