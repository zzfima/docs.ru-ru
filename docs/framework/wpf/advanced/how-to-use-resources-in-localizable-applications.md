---
title: Как использовать ресурсы в локализуемых приложениях
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 82a24feb4008b6cfd7c1751c6449c0d8515ffe87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544707"
---
# <a name="how-to-use-resources-in-localizable-applications"></a>Как использовать ресурсы в локализуемых приложениях
Локализация означает настройку [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для разных языков и региональных параметров. Для этого необходимо перевести названия, заголовки, элементы полей со списком и т. д. Чтобы облегчить перевод, переводимые элементы записываются в файлы ресурсов. В разделе [локализации приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) сведения о том, как создать файл ресурсов для локализации. Чтобы сделать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможность локализации, разработчики должны встроить все локализуемые ресурсы в сборку ресурсов приложения. Сборка ресурсов локализуется на разные языки, и код программной части использует управление ресурсами [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] для загрузки. Один из файлов, необходимых для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения — это файл проекта (".proj"). Все ресурсы, используемые в приложении, необходимо включить в файл проекта. Это показано в следующем примере кода.  
  
## <a name="example"></a>Пример  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Чтобы использовать ресурс в приложении, следует создать <xref:System.Resources.ResourceManager> и загрузки ресурсов, которые вы хотите использовать. Ниже показано, как это сделать.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
