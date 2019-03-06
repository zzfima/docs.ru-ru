---
title: Практическое руководство. Использование ресурсов в локализуемых приложениях
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: ad257e7703bcee8f71da78ad5928d7999365c38f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376169"
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="0c933-102">Практическое руководство. Использование ресурсов в локализуемых приложениях</span><span class="sxs-lookup"><span data-stu-id="0c933-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="0c933-103">Локализация означает адаптацию [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для разных языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="0c933-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="0c933-104">Для этого необходимо перевести названия, заголовки, элементы полей со списком и т. д.</span><span class="sxs-lookup"><span data-stu-id="0c933-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="0c933-105">Чтобы облегчить перевод, переводимые элементы записываются в файлы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0c933-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="0c933-106">См. в разделе [локализация приложения](how-to-localize-an-application.md) сведения о том, как создать файл ресурсов для локализации.</span><span class="sxs-lookup"><span data-stu-id="0c933-106">See [Localize an Application](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="0c933-107">Чтобы сделать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] локализуемым, разработчикам нужно объединить все локализуемые ресурсы в сборку ресурсов приложения.</span><span class="sxs-lookup"><span data-stu-id="0c933-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="0c933-108">Сборка ресурсов локализуется на разные языки, и код программной части использует модуль управления ресурсами [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] для загрузки.</span><span class="sxs-lookup"><span data-stu-id="0c933-108">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="0c933-109">Один из файлов, необходимых для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения — это файл проекта (.proj).</span><span class="sxs-lookup"><span data-stu-id="0c933-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="0c933-110">Все ресурсы, используемые в приложении, необходимо включить в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="0c933-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="0c933-111">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0c933-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c933-112">Пример</span><span class="sxs-lookup"><span data-stu-id="0c933-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="0c933-113">Чтобы использовать ресурс в своем приложении, следует создать <xref:System.Resources.ResourceManager> и загрузки ресурсов, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="0c933-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="0c933-114">Ниже показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="0c933-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
