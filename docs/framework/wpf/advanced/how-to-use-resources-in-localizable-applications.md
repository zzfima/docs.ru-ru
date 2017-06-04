---
title: "Как использовать ресурсы в локализуемых приложениях | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "приложения, локализуемое"
  - "локализуемые приложения"
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Как использовать ресурсы в локализуемых приложениях
Локализация означает настройку [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для различных языков и региональных параметров.  Для этого необходимо перевести названия, заголовки, элементы полей со списком и т.д.  Чтобы облегчить перевод, переводимые элементы записываются в файлы ресурсов.  См. раздел [Локализация приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) для получения сведений, как создать файл ресурсов для локализации.  Чтобы предоставить возможность локализации приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], разработчики должны встроить все локализуемые ресурсы в сборку ресурсов.  Сборка ресурсов локализуется на разные языки, и фоновый код использует API управления ресурсами [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] для загрузки.  Одним из файлов, необходимым для приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], является файл проекта \(PROJ\).  Все ресурсы, которые используются в приложении, должны быть включены в файл проекта.  Следующий пример кода показывает это.  
  
## Пример  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Для использования ресурсов в приложении, создайте экземпляр <xref:System.Resources.ResourceManager> и загрузите ресурс, который необходимо использовать.  Ниже показано, как это сделать.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]