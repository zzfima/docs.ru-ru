---
title: "Образец пакета шрифтов OpenType | Microsoft Docs"
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
  - "шрифты, пакет шрифтов OpenType"
  - "пакет шрифтов OpenType"
  - "оформление, пакет шрифтов OpenType"
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Образец пакета шрифтов OpenType
В этой теме предоставляется обзор образцов шрифтов [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], которые поставляются с [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)].  Шрифты образца поддерживают расширенные функции [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], которые могут использоваться приложениями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="overview"></a>   
## Шрифты в пакете шрифтов OpenType  
 [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] предоставляет набор образцов шрифтов [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], которые можно использовать при создании приложений [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Образцы шрифтов поставляются под лицензией Ascender Corporation.  Эти шрифты реализуют только подмножество общих функций, заданное форматом [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  В следующей таблице перечислены имена образцов шрифтов [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
|**Имя**|**Файл**|  
|-------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte полужирный|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles ненасыщенный|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero полужирный|Pescab.ttf|  
  
 На следующем рисунке показано, как выглядят образцы шрифтов [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
 ![Список имен шрифтов в примере пакета шрифтов](../../../../docs/framework/wpf/advanced/media/samplefontpack01.png "samplefontpack01")  
Шрифты в пакете шрифтов OpenType  
  
 Образцы шрифтов поставляются под лицензией Ascender Corporation.  Ascender является поставщиком шрифтов.  Для получения лицензии на расширенные или пользовательские версии образцов шрифтов см. [веб\-сайт корпорации Ascender](http://go.microsoft.com/fwlink/?LinkId=182627).  
  
> [!NOTE]
>  Ответственность разработчика состоит в том, чтобы гарантировать наличие требуемых лицензионных прав на любой шрифт, встраиваемый в приложение или распространяемый иными путями.  
  
<a name="installing_the_fonts"></a>   
## Установка шрифтов  
 Имеется возможность установки образцов шрифтов [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] в назначенный по умолчанию каталог шрифтов [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], **\\WINDOWS\\Fonts**.  Для установки этих шрифтов используется панель управления.  После установки шрифтов на компьютере они становятся доступны для всех приложений, которые ссылаются на шрифты [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] по умолчанию. Можно отобразить репрезентативный набор символов в нескольких размерах шрифта, дважды щелкнув файл шрифта.  На следующем снимке экрана показан файл шрифта Lindsey, Linds.ttf.  
  
 ![Шрифт Lindsey &#40;OpenType&#41;](../../../../docs/framework/wpf/advanced/media/typographyinwpf-04.png "TypographyInWPF\_04")  
Отображение шрифта Lindsey  
  
<a name="using_the_fonts"></a>   
## Использование шрифтов  
 Есть два способа использования шрифтов в приложении.  Можно добавить шрифты в приложение в виде элементов содержимого проекта, которые не внедрены в сборку как ресурсы.  Кроме того, можно добавлять шрифты в приложение в виде элементов ресурсов проекта, которые внедрены в файлы сборки приложения.  Дополнительные сведения см. в разделе [Упаковка шрифтов с приложениями](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md).  
  
## См. также  
 <xref:System.Windows.Documents.Typography>   
 [Возможности шрифта OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md)   
 [Упаковка шрифтов с приложениями](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)