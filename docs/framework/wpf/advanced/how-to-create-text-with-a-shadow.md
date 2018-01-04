---
title: "Практическое руководство. Создание текста с тенью"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b031b0dce8e1fd06399ded0b6d612a23323ae837
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-text-with-a-shadow"></a>Практическое руководство. Создание текста с тенью
Примеры в этом разделе демонстрируют создание эффекта тени для отображаемого текста.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Media.Effects.DropShadowEffect> Объектов позволяет создавать разнообразные эффекты тени для [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] объектов. В следующем примере показано применение эффекта тени к тексту. В этом случае используется мягкая тень, то есть цвет тени размывается.  
  
 ![Тень текста с мягкостью &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
Пример текста с мягкой тенью  
  
 Можно задать ширину тени, установив <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> свойство. Значение `4.0` указывает ширину тени 4 пикселя. Можно управлять плавность или размытия тени, изменяя <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> свойство. Значение `0.0` указывает отсутствие размытия. В следующем примере кода показано создание мягкой тени.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Эти эффекты тени не проходят через [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] конвейера отрисовки текста. Следовательно, тип ClearType при использовании этих эффектов отключен.  
  
 В следующем примере показано применение эффекта жесткой тени к тексту. В этом случае тень не размыта.  
  
 ![Тень текста с мягкостью &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")  
Пример текста с жесткой тенью  
  
 Жесткой тени можно создать, присвоив <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> свойства `0.0`, который показывает, что отсутствие размытия. Можно управлять направлением тени, изменяя <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> свойство. Значение этого свойства угол между `0` и `360`. На следующем рисунке показан направления значения <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> значение свойства.  
  
 ![Параметр степени тени DropShadow](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
Схема направления DropShadow  
  
 В следующем примере кода показано создание жесткой тени.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Использование эффекта размытия  
 Объект <xref:System.Windows.Media.Effects.BlurBitmapEffect> можно использовать для создания эффекта аналогичный тени, который можно поместить позади текстового объекта. Если к тексту применяется эффект размытия для точечных рисунков, текст равномерно размывается во всех направлениях.  
  
 В следующем примере показан эффект размытия, примененный к тексту.  
  
 ![Тень текста с использованием BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
Пример текста с эффектом размытия  
  
 В следующем примере кода показано создание эффекта размытия.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Использование преобразования переноса  
 Объект <xref:System.Windows.Media.TranslateTransform> можно использовать для создания эффекта аналогичный тени, который можно поместить позади текстового объекта.  
  
 Следующий пример кода использует <xref:System.Windows.Media.TranslateTransform> для смещения текста. В этом примере слегка смещенная копия текста под основным текстом создает эффект тени.  
  
 ![Тень текста с использованием TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")  
Пример текста, в котором преобразование используется для создания эффекта тени  
  
 В следующем примере кода показано создание эффекта тени с помощью преобразования.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
