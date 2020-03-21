---
title: Практическое руководство. Создание текста с тенью
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: c3e8135372ce4a092552c812cd971cb70bc49bf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186851"
---
# <a name="how-to-create-text-with-a-shadow"></a>Практическое руководство. Создание текста с тенью
Примеры в этом разделе демонстрируют создание эффекта тени для отображаемого текста.  
  
## <a name="example"></a>Пример  
 Объект <xref:System.Windows.Media.Effects.DropShadowEffect> позволяет создавать различные эффекты тени [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] падения для объектов. В следующем примере показано применение эффекта тени к тексту. В этом случае используется мягкая тень, то есть цвет тени размывается.  
  
 ![Текстовая тень с мягкостью &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 Вы можете управлять шириной тени, <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> установив свойство. Значение `4.0` указывает на ширину тени 4 пикселя. Вы можете контролировать мягкость, или размытие, <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> тени, изменяя свойство. Значение `0.0` указывает на отсутствие размытия. В следующем примере кода показано создание мягкой тени.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> Эти эффекты теней [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] не проходят через конвейер визуализации текста. Следовательно, тип ClearType при использовании этих эффектов отключен.  
  
 В следующем примере показано применение эффекта жесткой тени к тексту. В этом случае тень не размыта.  
  
 ![Текстовая тень с мягкостью &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 Можно создать твердую тень, <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> установив `0.0`свойство, что указывает на то, что размытие не используется. Вы можете управлять направлением тени, <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> изменяя свойство. Установите направленную стоимость этого свойства `0` в `360`определенной степени между и . На следующей иллюстрации показаны <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> значения направления настройки свойства.  
  
 ![Параметр степени тени DropShadow](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 В следующем примере кода показано создание жесткой тени.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Использование эффекта размытия  
 A <xref:System.Windows.Media.Effects.BlurBitmapEffect> может быть использован для создания эффекта, похожего на тени, который может быть размещен за текстовым объектом. Если к тексту применяется эффект размытия для точечных рисунков, текст равномерно размывается во всех направлениях.  
  
 В следующем примере показан эффект размытия, примененный к тексту.  
  
 ![Тень текста с использованием BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 В следующем примере кода показано создание эффекта размытия.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Использование преобразования переноса  
 A <xref:System.Windows.Media.TranslateTransform> может быть использован для создания эффекта, похожего на тени, который может быть размещен за текстовым объектом.  
  
 В следующем примере <xref:System.Windows.Media.TranslateTransform> кода используется для смещения текста. В этом примере слегка смещенная копия текста под основным текстом создает эффект тени.  
  
 ![Тень текста с использованием TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 В следующем примере кода показано создание эффекта тени с помощью преобразования.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
