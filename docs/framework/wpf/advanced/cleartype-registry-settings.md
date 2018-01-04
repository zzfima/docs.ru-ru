---
title: "Параметры реестра ClearType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d915af4ee436bb6c661a7b412b0e36702191339a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cleartype-registry-settings"></a>Параметры реестра ClearType
В этом разделе содержится обзор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] параметры реестра, которые используются в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений.  
  
  
<a name="overview"></a>   
## <a name="technology-overview"></a>Общие сведения о технологии  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]приложения, которые отображают текст на устройстве отображения, используют [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] функции для предоставления расширенного. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] — это программная технология, разработанная [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] для улучшения удобочитаемости текста на современных ЖК-мониторах (жидкокристаллических дисплеях), например экранах ноутбуков, карманных ПК и плоскопанельных мониторах. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] работает путем обращения к отдельным элементам вертикальных цветных полос в каждом пикселе ЖК-экрана. Дополнительные сведения о [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], в разделе [Обзор ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md).  
  
 Текст, отображаемый с [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] может существенно отличаться при просмотре на различных устройствах отображения. Например, небольшое число мониторов реализуют элементы цветных полос в порядке, красный, зеленый, синий, а не чаще, красный, зеленый, синий ( [!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]) порядке.  
  
 Текст, отображаемый с [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] может также существенно отличаться при просмотрах с различными уровнями чувствительности цвет. Некоторые замечают незначительные различия в цвете лучше, чем другие.  
  
 В каждом из этих случаев [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] функции должны быть изменены, чтобы обеспечить лучшее изображение для каждого пользователя.  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a>Параметры реестра  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Указывает четыре параметра реестра для управления [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] функции:  
  
|Параметр|Описание:|  
|-------------|-----------------|  
|Уровень [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]|Описывает уровень [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] прозрачности цвета.|  
|Гамма-уровень|Описывает уровень компонента цвета пикселя для устройства отображения.|  
|Структура пикселей|Описывает расположение пикселей для устройства отображения.|  
|Уровень контрастности текста|Описывает уровень контрастности отображаемого текста.|  
  
 Эти параметры доступны программы внешней конфигурации, который знает, как ссылаться на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] параметры реестра. Эти параметры также можно создать или изменить через прямой доступ к значениям с использованием редактора реестра [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 Если [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] (это состояние по умолчанию), не установлены параметры реестра [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] запросов приложения [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] системные параметры сведения для настройки сглаживания шрифтов.  
  
> [!NOTE]
>  Сведения о перечислении отображаемые имена устройств см. в разделе `SystemParametersInfo` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] функции.  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a>Уровень ClearType  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Уровень позволяет настраивать отрисовку текста на основе регистра цвет и восприятия пользователя. Для некоторых пользователей отрисовка текста, которая использует [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] на самом высоком уровне не создает лучшие возможности для чтения.  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] Уровень — это целочисленное значение, в диапазоне от 0 до 100. По умолчанию — 100, что означает [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] использует максимальные возможности элементов чередующиеся цвета дисплея. Тем не менее [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] уровень 0 отображает текст в виде оттенков серого. Установив [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] уровня где-нибудь между 0 и 100, можно создать промежуточный уровень, подходящий для отдельного цвета чувствительности.  
  
### <a name="registry-setting"></a>Параметр реестра  
 Параметр реестра для [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] уровня — параметр отдельного пользователя, который соответствует определенному имени дисплея:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Для каждого названия дисплея для пользователя `ClearTypeLevel` определено значение DWORD. На следующем рисунке показан редактор реестра параметр [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] уровне.  
  
 ![Параметры ClearType в редакторе реестра](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]приложения для вывода текста в одном из двух режимов, с и без [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]. Отображение текста без [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], он называется отрисовки оттенков серого.  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a>Гамма-уровень  
 Гамма-уровень относится к нелинейной связи между значением пикселя и яркостью. Параметр гамма-уровня должен соответствовать физическим характеристикам устройства отображения; в противном случае возможны нарушения в отрисовываемых выходных данных. Например, текст может отображаться слишком широко или узко, либо по краям вертикальных полос глифов могут отображаться цветные полосы.  
  
 Гамма-уровень — это целочисленное значение в диапазоне от 1000 до 2200. Значение по умолчанию — 1900.  
  
### <a name="registry-setting"></a>Параметр реестра  
 Расположение параметра реестра для гамма-уровня — параметр локальной машины, соответствующий имени определенного устройства отображения.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Для каждого названия дисплея для пользователя `GammaLevel` определено значение DWORD. На следующем снимке экрана показан параметр редактора реестра для гамма-уровня.  
  
 ![Параметры ClearType в редакторе реестра](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a>Структура пикселей  
 Структура пикселей описывает тип пикселей, составляющих устройство отображения. Структура пикселей определяется как один из трех типов.  
  
|Тип|Значение|Описание:|  
|----------|-----------|-----------------|  
|плоский|0|Устройство отображения не имеет структуры пикселей. Это означает, что источники света для каждого цвета распределены равномерно в области пикселя: это называется отрисовкой в оттенках серого. Так работает стандартное устройство отображения. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] никогда не применяется к отрисованному тексту.|  
|RGB|1|Пиксели на устройстве отображения состоят из трех полос, расположенных в следующем порядке: красный, зеленый и синий. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] применяется к отрисованному тексту.|  
|BGR|2|Пиксели на устройстве отображения состоят из трех полос, расположенных в следующем порядке: синий, зеленый и красный. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] применяется к отрисованному тексту. Обратите внимание на обратный порядок цветов по сравнению с RGB.|  
  
 Структура пикселей соответствует целочисленному значению в диапазоне от 0 до 2. Значение по умолчанию — 0, представляющее плоскую структуру пикселей.  
  
> [!NOTE]
>  Сведения о перечислении отображаемые имена устройств см. в разделе `EnumDisplayDevices` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] функции.  
  
### <a name="registry-setting"></a>Параметр реестра  
 Расположение параметра реестра для структуры пикселей — параметр локальной машины, соответствующий имени определенного устройства отображения.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Для каждого названия дисплея для пользователя `PixelStructure` определено значение DWORD. На следующем снимке экрана показан параметр редактора реестра для структуры пикселей.  
  
 ![Параметры ClearType в редакторе реестра](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a>Уровень контрастности текста  
 Уровень контрастности текста позволяет настроить отрисовку текста в зависимости от ширины полос глифов. Уровень контрастности текста — это целочисленное значение в диапазоне от 0 до 6: чем больше это значение, тем шире полоса. Значение по умолчанию — 1.  
  
### <a name="registry-setting"></a>Параметр реестра  
 Параметр реестра для уровня контрастности текста расположен в параметре отдельного пользователя, соответствующем имени определенного устройства отображения.  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Для каждого названия дисплея для пользователя `TextContrastLevel` определено значение DWORD. На следующем снимке экрана показан параметр редактора реестра для уровня контрастности текста.  
  
 ![Параметры ClearType в редакторе реестра](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о технологии ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md)  
 [Сглаживание ClearType](https://msdn.microsoft.com/library/dd183433(v=vs.85).aspx)
