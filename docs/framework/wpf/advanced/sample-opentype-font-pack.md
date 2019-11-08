---
title: Образец пакета шрифтов OpenType
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: a5b49e2a1f7536fb9d8e8f4dbfc53494dcd1f1ac
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740770"
---
# <a name="sample-opentype-font-pack"></a>Образец пакета шрифтов OpenType
В этом разделе приводятся общие сведения о примерах шрифтов OpenType, распространяемых вместе с Windows SDK. Образцы шрифтов поддерживают расширенные функции OpenType, которые могут использоваться приложениями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

<a name="overview"></a>   
## <a name="fonts-in-the-opentype-font-pack"></a>Шрифты в пакете шрифтов OpenType  
 Windows SDK предоставляет набор образцов шрифтов OpenType, которые можно использовать при создании [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложений. Образцы шрифтов предоставляются по лицензии от Ascender Corporation. Эти шрифты реализуют только подмножество всех функций, определенных в формате OpenType. В следующей таблице перечислены имена образцов шрифтов OpenType.  
  
|**Name**|**Файл**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Bold|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero Bold|Pescab.ttf|  
  
 На следующем рисунке показано, как выглядят примеры шрифтов OpenType.  
  
 ![Список имен шрифтов в примере пакета шрифтов](./media/sample-opentype-font-pack/font-names-sample-pack.gif)  
  
 Образцы шрифтов предоставляются по лицензии от Ascender Corporation. Ascender является поставщиком передовых решений для шрифтов. Для лицензирования расширенных или настраиваемых версий образцов шрифтов см. [веб-сайт корпорации Ascender](https://go.microsoft.com/fwlink/?LinkId=182627).  
  
> [!NOTE]
> Являясь разработчиком, вы несете ответственность за наличие у вас необходимых лицензионных прав на любой шрифт, который вы включаете в приложение или распространяете иным образом.  
  
<a name="installing_the_fonts"></a>   
## <a name="installing-the-fonts"></a>Установка шрифтов  
 Вы можете установить образцы шрифтов OpenType в каталог шрифтов Windows по умолчанию **\виндовс\фонтс**. Для установки шрифтов используйте панель управления Fonts. После того как эти шрифты будут установлены на компьютере, они будут доступны для всех приложений, которые ссылаются на шрифты Windows по умолчанию. Можно отобразить характерный набор символов в нескольких размерах шрифта, дважды нажав файл шрифта. На следующем снимке экрана показан файл шрифта Lindsey, Linds.ttf.  
  
 ![Lindsey font &#40;OpenType&#41;](./media/typographyinwpf-04.png "TypographyInWPF_04")  
Отображение шрифта Lindsey  
  
<a name="using_the_fonts"></a>   
## <a name="using-the-fonts"></a>Использование шрифтов  
 Есть два способа использования шрифтов в вашем приложении. Можно добавить шрифты в приложение в виде элементов содержимого проекта, которые не внедряются в качестве ресурсов в сборку. Кроме того, можно добавить шрифты в приложение в виде элементов ресурсов проекта, которые внедряются в файлы сборки приложения. Дополнительные сведения см. в разделе [Упаковка шрифтов с приложениями](packaging-fonts-with-applications.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Documents.Typography>
- [Возможности шрифта OpenType](opentype-font-features.md)
- [Упаковка шрифтов с приложениями](packaging-fonts-with-applications.md)
