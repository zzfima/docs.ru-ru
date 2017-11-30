---
title: "Как использовать ресурсы в локализуемых приложениях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d803989292e2fc6b0945c397df5ce32d318147fc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="7a125-102">Как использовать ресурсы в локализуемых приложениях</span><span class="sxs-lookup"><span data-stu-id="7a125-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="7a125-103">Локализация означает настройку [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для разных языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="7a125-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="7a125-104">Для этого необходимо перевести названия, заголовки, элементы полей со списком и т. д.</span><span class="sxs-lookup"><span data-stu-id="7a125-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="7a125-105">Чтобы облегчить перевод, переводимые элементы записываются в файлы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7a125-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="7a125-106">В разделе [локализации приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) сведения о том, как создать файл ресурсов для локализации.</span><span class="sxs-lookup"><span data-stu-id="7a125-106">See [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="7a125-107">Чтобы сделать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможность локализации, разработчики должны встроить все локализуемые ресурсы в сборку ресурсов приложения.</span><span class="sxs-lookup"><span data-stu-id="7a125-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="7a125-108">Сборка ресурсов локализуется на разные языки, и код программной части использует управление ресурсами [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] для загрузки.</span><span class="sxs-lookup"><span data-stu-id="7a125-108">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="7a125-109">Один из файлов, необходимых для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения — это файл проекта (".proj").</span><span class="sxs-lookup"><span data-stu-id="7a125-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="7a125-110">Все ресурсы, используемые в приложении, необходимо включить в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="7a125-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="7a125-111">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="7a125-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a125-112">Пример</span><span class="sxs-lookup"><span data-stu-id="7a125-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="7a125-113">Чтобы использовать ресурс в приложении, следует создать <xref:System.Resources.ResourceManager> и загрузки ресурсов, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="7a125-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="7a125-114">Ниже показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="7a125-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
