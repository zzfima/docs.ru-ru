---
title: Практическое руководство. Использование ресурсов в локализуемых приложениях
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 3634bb72cbacfb02b0a1230a47a1664cb8ce5009
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238464"
---
# <a name="how-to-use-resources-in-localizable-applications"></a>Практическое руководство. Использование ресурсов в локализуемых приложениях
Локализация означает адаптацию [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для разных языков и региональных параметров. Для этого необходимо перевести названия, заголовки, элементы полей со списком и т. д. Чтобы облегчить перевод, переводимые элементы записываются в файлы ресурсов. См. в разделе [локализация приложения](how-to-localize-an-application.md) сведения о том, как создать файл ресурсов для локализации. Чтобы сделать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] локализуемым, разработчикам нужно объединить все локализуемые ресурсы в сборку ресурсов приложения. Сборка ресурсов локализуется на разные языки, и код программной части использует API управления ресурсами для загрузки. Один из файлов, необходимых для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения — это файл проекта (.proj). Все ресурсы, используемые в приложении, необходимо включить в файл проекта. Это показано в следующем примере кода.  
  
## <a name="example"></a>Пример  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Чтобы использовать ресурс в своем приложении, следует создать <xref:System.Resources.ResourceManager> и загрузки ресурсов, которые вы хотите использовать. Ниже показано, как это сделать.  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
