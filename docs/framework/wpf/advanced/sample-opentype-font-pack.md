---
title: Образец пакета шрифтов OpenType
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: 30cb69fcf05108822e8f3e2d45c9e79dbced26ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181909"
---
# <a name="sample-opentype-font-pack"></a>Образец пакета шрифтов OpenType
В этой теме представлен обзор образца шрифтов OpenType, которые распространяются с помощью Windows SDK. Образец шрифтов поддерживает расширенные функции [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] OpenType, которые могут быть использованы приложениями.  

<a name="overview"></a>
## <a name="fonts-in-the-opentype-font-pack"></a>Шрифты в пакете шрифтов OpenType  
 SDK Windows предоставляет набор примеров шрифтов OpenType, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] которые можно использовать при создании приложений. Образцы шрифтов предоставляются по лицензии от Ascender Corporation. Эти шрифты реализуют только подмножество общих функций, определенных форматом OpenType. В следующей таблице перечислены имена шрифтов OpenType.  
  
|**Название**|**Файл**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Bold|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero Bold|Pescab.ttf|  
  
 На следующей иллюстрации показано, как выглядят образцы шрифтов OpenType.  
  
 ![Список имен шрифтов в примере пакета шрифтов](./media/sample-opentype-font-pack/font-names-sample-pack.gif)  
  
 Образцы шрифтов предоставляются по лицензии от Ascender Corporation. Ascender является поставщиком передовых решений для шрифтов. Для лицензирования расширенных или настраиваемых версий образцов шрифтов см. [веб-сайт корпорации Ascender](https://www.monotype.com/).  
  
> [!NOTE]
> Являясь разработчиком, вы несете ответственность за наличие у вас необходимых лицензионных прав на любой шрифт, который вы включаете в приложение или распространяете иным образом.  
  
<a name="installing_the_fonts"></a>
## <a name="installing-the-fonts"></a>Установка шрифтов  
 У вас есть возможность установки образца шрифтов OpenType в каталог шрифтов Windows по умолчанию, **sWINDOWS-Fonts.** Для установки шрифтов используйте панель управления Fonts. После того, как эти шрифты находятся на вашем компьютере, они доступны для всех приложений, которые ссылаются на шрифты Windows по умолчанию. Можно отобразить характерный набор символов в нескольких размерах шрифта, дважды нажав файл шрифта. На следующем снимке экрана показан файл шрифта Lindsey, Linds.ttf.  
  
 ![Lindsey font &#40;OpenType&#41;](./media/typographyinwpf-04.png "TypographyInWPF_04")  
Отображение шрифта Lindsey  
  
<a name="using_the_fonts"></a>
## <a name="using-the-fonts"></a>Использование шрифтов  
 Есть два способа использования шрифтов в вашем приложении. Можно добавить шрифты в приложение в виде элементов содержимого проекта, которые не внедряются в качестве ресурсов в сборку. Кроме того, можно добавить шрифты в приложение в виде элементов ресурсов проекта, которые внедряются в файлы сборки приложения. Дополнительные сведения см. в разделе [Упаковка шрифтов с приложениями](packaging-fonts-with-applications.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Documents.Typography>
- [Возможности шрифта OpenType](opentype-font-features.md)
- [Упаковка шрифтов с приложениями](packaging-fonts-with-applications.md)
