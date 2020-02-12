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
# <a name="passing-a-uri-to-the-windows-runtime"></a>Передача URI в среду выполнения Windows
Методы среды выполнения Windows принимают только абсолютные URI. Если в метод среда выполнения Windows передается относительный URI, возникает исключение <xref:System.ArgumentException>. Вот почему: при использовании среда выполнения Windows в .NET Frameworkном коде класс <xref:Windows.Foundation.Uri?displayProperty=nameWithType> отображается как <xref:System.Uri?displayProperty=nameWithType> в IntelliSense. Класс <xref:System.Uri?displayProperty=nameWithType> допускает относительные URI, но класс <xref:Windows.Foundation.Uri?displayProperty=nameWithType> не имеет. Это также справедливо для методов, предоставляемых в среда выполнения Windowsных компонентах. Если компонент предоставляет метод, принимающий URI, сигнатура в коде содержит <xref:System.Uri?displayProperty=nameWithType>. Однако для пользователей компонента подпись включает <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. URI, переданный вашему компоненту, должен быть абсолютным.  
  
В этом разделе показано, как определить абсолютный URI и как создать его при указании ссылки на ресурс в пакете приложения.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Определение и использование абсолютного URI  
Используйте свойство <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>, чтобы убедиться, что URI является абсолютным, прежде чем передать его в среда выполнения Windows. Такой подход более эффективен, чем перехват и обработка исключения <xref:System.ArgumentException>.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Использование абсолютного URI для ресурса в пакете приложения  
Чтобы указать URI для ресурса в пакете приложения, можно использовать схему `ms-appx` или `ms-appx-web` для создания абсолютного URI.  
  
В следующем примере показано, как задать свойство <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> для элемента управления <xref:Windows.UI.Xaml.Controls.WebView> и свойство <xref:Windows.UI.Xaml.Controls.Image.Source%2A> для элемента управления <xref:Windows.UI.Xaml.Controls.Image> для ресурсов, содержащихся в папке Pages, с использованием XAML и кода.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Дополнительные сведения об этих схемах см. в разделе [схемы URI](/windows/uwp/app-resources/uri-schemes) в центре разработки для Windows.  
  
## <a name="see-also"></a>См. также раздел

- [Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
