---
title: "Практическое руководство. Создание текста с тенью | Microsoft Docs"
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
  - "эффекты тени в тексте"
  - "текст, затененные"
  - "оформление, эффекты тени"
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Создание текста с тенью
В примерах этого раздела показано, как создать эффект тени для отображаемого текста.  
  
## Пример  
 Объект <xref:System.Windows.Media.Effects.DropShadowEffect> позволяет создавать разнообразные эффекты тени для объектов [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  В следующем примере показан эффект тени, применяемый к тексту.  В этом случае тень является мягкой, что означает размытие цвета тени.  
  
 ![Тень текста с мягкостью &#61; 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.png "ShadowText01")  
Пример текста с мягкой тенью  
  
 Можно управлять шириной тени, задавая значение свойства <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>.  Значение `4.0` указывает ширину тени равную 4 пикселям.  Можно управлять резкостью или размытием тени, изменяя свойство <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>.  Значение `0.0` указывает отсутствие размытия.  В следующем примере показан способ создания мягкой тени.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Эти эффекты тени не проходят через конвейер отрисовки текста [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  В результате, при использовании этих эффектов отключается технология ClearType.  
  
 В следующем примере показан эффект жесткой тени, применяемый к тексту.  В этом случае тень не размыта.  
  
 ![Тень текста с мягкостью &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.png "ShadowText02")  
Пример текста с жесткой тенью  
  
 Можно создать жесткую тень, присвоив свойству <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> значение `0.0`, которое указывает, что эффект размытия не используется.  Можно управлять направлением тени, изменяя свойство <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>.  Значение этого свойства представляет собой угол между `0` и `360`.  На следующем рисунке показаны значения направления для свойства <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>.  
  
 ![Параметр степени тени DropShadow](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
Схема направления объекта DropShadow  
  
 В следующем примере показан способ создания жесткой тени.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## Использование эффекта размытия  
 С помощью объекта <xref:System.Windows.Media.Effects.BlurBitmapEffect> можно создать аналогичный тени эффект, который можно поместить позади текстового объекта.  Эффект размытия, примененный к тексту, размывает текст равномерно во всех направлениях.  
  
 В следующем примере показан эффект размытия, примененный к тексту.  
  
 ![Тень текста с использованием BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.png "ShadowText06")  
Пример текста с эффектом размытия  
  
 В следующем примере кода показан способ создания эффекта размытия.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## Использование преобразования со смещением  
 Объект <xref:System.Windows.Media.TranslateTransform> можно использовать для создания эффекта, похожего на тень, который можно поместить позади объекта текста.  
  
 В следующем примере кода используется объект <xref:System.Windows.Media.TranslateTransform> для смещения текста.  В этом примере немного смещенная копия текста под основным текстом создает эффект тени.  
  
 ![Тень текста с использованием TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.png "ShadowText07")  
Пример текста с использованием преобразования для создания эффекта тени  
  
 В следующем примере показано, как создать преобразование для создания эффекта тени.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]