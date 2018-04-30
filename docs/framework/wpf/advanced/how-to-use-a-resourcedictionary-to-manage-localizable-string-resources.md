---
title: Практическое руководство. Использование ResourceDictionary для управления локализуемыми строковыми ресурсами
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 70f8f02f315580c8056ee698b5e45b1a31a3dc74
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="bf781-102">Практическое руководство. Использование ResourceDictionary для управления локализуемыми строковыми ресурсами</span><span class="sxs-lookup"><span data-stu-id="bf781-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="bf781-103">В этом примере показано, как использовать <xref:System.Windows.ResourceDictionary> для пакетов локализуемых строковых ресурсов для приложений Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="bf781-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="bf781-104">Использование ResourceDictionary для управления локализуемыми строковыми ресурсами</span><span class="sxs-lookup"><span data-stu-id="bf781-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1.  <span data-ttu-id="bf781-105">Создание <xref:System.Windows.ResourceDictionary> , содержащий строки требуется локализовать.</span><span class="sxs-lookup"><span data-stu-id="bf781-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="bf781-106">Вот пример кода:</span><span class="sxs-lookup"><span data-stu-id="bf781-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="bf781-107">Этот код определяет ресурс строки `localizedMessage`, типа <xref:System.String>, из <xref:System> пространства имен в библиотеке mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="bf781-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2.  <span data-ttu-id="bf781-108">Добавить <xref:System.Windows.ResourceDictionary> к приложению, используя следующий код.</span><span class="sxs-lookup"><span data-stu-id="bf781-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  <span data-ttu-id="bf781-109">Используйте строковый ресурс из разметки, с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bf781-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  <span data-ttu-id="bf781-110">Используйте строковый ресурс из файла кода программной части с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="bf781-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  <span data-ttu-id="bf781-111">Локализуйте приложение.</span><span class="sxs-lookup"><span data-stu-id="bf781-111">Localize the application.</span></span> <span data-ttu-id="bf781-112">Дополнительные сведения см. в разделе [локализации приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="bf781-112">For more information, see [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span></span>
