---
title: "Передача URI в среду выполнения Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "среда выполнения Windows, поддержка .NET Framework для"
  - "среда выполнения Windows, передача URI в"
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Передача URI в среду выполнения Windows
Методы среды выполнения Windows принимают только абсолютные URI. Если передать относительный URI методу [!INCLUDE[wrt](../../../includes/wrt-md.md)], вызывается исключение <xref:System.ArgumentException>. Это происходит из\-за того, что при использовании [!INCLUDE[wrt](../../../includes/wrt-md.md)] в коде .NET Framework класс [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) отображается в Intellisense как <xref:System.Uri?displayProperty=fullName>. Класс <xref:System.Uri?displayProperty=fullName> допускает относительные URI, а класс [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) — нет. Это также справедливо для методов, доступных в компонентах [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Если компонент предоставляет метод, принимающий URI, сигнатура в коде содержит <xref:System.Uri?displayProperty=fullName>. Однако для пользователей вашего компонента сигнатура содержит [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376). URI, переданный вашему компоненту, должен быть абсолютным.  
  
 В этом разделе показано, как определить абсолютный URI и как создать его при указании ссылки на ресурс в пакете приложения.  
  
## Определение и использование абсолютного URI  
 Используйте свойство <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=fullName>, чтобы убедиться, что URI является абсолютным, перед его передачей классу [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Такой подход более эффективен, чем перехват и обработка исключения <xref:System.ArgumentException>.  
  
## Использование абсолютного URI для ресурса в пакете приложения  
 Чтобы указать URI для ресурса в пакете приложения, можно использовать схему `ms-appx` или `ms-appx-web` для создания абсолютного URI.  
  
 В следующем примере показано, как задать свойство [Source](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) для элемента управления [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) и свойство [Source](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) для элемента управления [Image](http://msdn.microsoft.com/library/windows/apps/br242752.aspx), указав ресурсы из папки Pages, с использованием как XAML, так и кода.  
  
 [!code-xml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 Дополнительные сведения об этих схемах см. в статье [Схемы URI](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) в Центре разработки для Windows.  
  
## См. также  
 [Поддержка приложений для Магазина Windows и среды выполнения Windows в .NET Framework](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)