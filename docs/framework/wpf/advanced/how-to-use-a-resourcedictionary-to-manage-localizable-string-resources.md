---
title: Практическое руководство. Использование ResourceDictionary для управления локализуемыми строковыми ресурсами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: b56a307ed31fc8f7573215eac70350ac5e4b9de1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772119"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="45bb4-102">Практическое руководство. Использование ResourceDictionary для управления локализуемыми строковыми ресурсами</span><span class="sxs-lookup"><span data-stu-id="45bb4-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="45bb4-103">В этом примере показано, как использовать <xref:System.Windows.ResourceDictionary> для пакетов локализуемых строковых ресурсов для приложений Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="45bb4-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="45bb4-104">Использование ResourceDictionary для управления локализуемыми строковыми ресурсами</span><span class="sxs-lookup"><span data-stu-id="45bb4-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1. <span data-ttu-id="45bb4-105">Создание <xref:System.Windows.ResourceDictionary> , содержащую строки, чтобы локализовать.</span><span class="sxs-lookup"><span data-stu-id="45bb4-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="45bb4-106">Вот пример кода:</span><span class="sxs-lookup"><span data-stu-id="45bb4-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="45bb4-107">Этот код определяет строковый ресурс, `localizedMessage`, типа <xref:System.String>, из <xref:System> пространства имен в библиотеке mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="45bb4-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2. <span data-ttu-id="45bb4-108">Добавление <xref:System.Windows.ResourceDictionary> для вашего приложения, используя следующий код.</span><span class="sxs-lookup"><span data-stu-id="45bb4-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. <span data-ttu-id="45bb4-109">Используйте строковый ресурс из разметки, используя [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] следующим образом.</span><span class="sxs-lookup"><span data-stu-id="45bb4-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. <span data-ttu-id="45bb4-110">Используйте строковый ресурс из файла кода программной части с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="45bb4-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. <span data-ttu-id="45bb4-111">Локализуйте приложение.</span><span class="sxs-lookup"><span data-stu-id="45bb4-111">Localize the application.</span></span> <span data-ttu-id="45bb4-112">Дополнительные сведения см. в разделе [локализация приложения](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="45bb4-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>
