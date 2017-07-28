---
title: "Использование стеклянной рамки в приложении WPF | Microsoft Docs"
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
  - "приложения, расширение стеклянных фреймов"
  - "расширение стеклянных фреймов в приложения"
  - "стеклянные фреймы, расширение в приложения"
  - "графика, расширение стеклянных фреймов в приложения"
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Использование стеклянной рамки в приложении WPF
В этом разделе показано, как расширить стеклянный фрейм [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] в клиентской области приложения [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
> [!NOTE]
>  Этот пример будет работать только на компьютере под управлением [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)], на котором выполняется диспетчер окон рабочего стола \(DWM\) с включенным эффектом прозрачного стекла.  Выпуск [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] Home Basic не поддерживает эффект прозрачного стекла.  Области, которые в других выпусках [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] обычно отображаются с эффектом прозрачного стекла, отображаются непрозрачными.  
  
## Пример  
 На следующем рисунке показан расширенный стеклянный фрейм в адресной строке Internet Explorer 7.  
  
 **Internet Explorer с расширенным стеклянным фреймом позади адресной строки.**  
  
 ![IE7 с прозрачным фреймом, расширенный за адресной строкой.](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")  
  
 Чтобы расширить стеклянный фрейм в приложении [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], необходим доступ к неуправляемому [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)].  Следующий пример кода выполняет платформенный вызов \(PInvoke\) для двух [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], необходимый для расширения фрейма в клиентскую область.  Каждый из этих [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] объявляется в классе с именем **NonClientRegionAPI**.  
  
<!-- TODO: review snippet reference  [!CODE [AvalonClientGlass#DWMExtendFramePInvokeAPI](AvalonClientGlass#DWMExtendFramePInvokeAPI)]  -->  
  
 [DwmExtendFrameIntoClientArea](_udwm_dwmextendframeintoclientarea) [](_udwm_dwmextendframeintoclientarea) является функцией диспетчера окон рабочего стола, которая расширяет фрейм до размера клиентской области.  Функция принимает два параметра: дескриптор окна и структуру [MARGINS](inet_MARGINS).  Структура [MARGINS](inet_MARGINS) используется для того, чтобы сообщить диспетчеру окон рабочего стола, насколько следует расширить фрейм в клиентской области.  
  
## Пример  
 Для использования функции [DwmExtendFrameIntoClientArea](_udwm_dwmextendframeintoclientarea) необходимо получить дескриптор окна.  В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] дескриптор окна может быть получен из свойства <xref:System.Windows.Interop.HwndSource.Handle%2A> объекта <xref:System.Windows.Interop.HwndSource>.  В следующем примере фрейм расширяется в клиентскую область при возникновении события окна <xref:System.Windows.FrameworkElement.Loaded>.  
  
<!-- TODO: review snippet reference  [!CODE [AvalonClientGlass#AvalonGlassOnLoadedCSharp](AvalonClientGlass#AvalonGlassOnLoadedCSharp)]  -->  
  
## Пример  
 В следующем примере показано простое окно, в котором фрейм расширяется в клиентскую область.  Фрейм расширяется за пределы верхней границы, содержащей два объекта <xref:System.Windows.Controls.TextBox>.  
  
<!-- TODO: review snippet reference  [!CODE [AvalonClientGlass#AvalonGlassFullWindowXAML](AvalonClientGlass#AvalonGlassFullWindowXAML)]  -->  
  
 На следующем рисунке показан стеклянный фрейм, расширенная в приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 **Прозрачный фрейм, расширенный в приложение**  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] **.**  
  
 ![Прозрачный фрейм, расширенная в приложение WPF.](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.png "WPFextendedGlassIntoClient")  
  
## См. также  
 [Общие сведения о диспетчере окон рабочего стола](_udwm_overview)   
 [Общие сведения об использовании эффекта размытия в диспетчере окон рабочего стола](_udwm_blur_ovw)   
 [DwmExtendFrameIntoClientArea](_udwm_dwmextendframeintoclientarea)