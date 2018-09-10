---
title: Рекомендации по безопасности XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: fea695be-617c-4977-9567-140e820436fc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fb7b096a6e9bf0f71649f260c4097d5e25476957
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44210962"
---
# <a name="xslt-security-considerations"></a>Рекомендации по безопасности XSLT
Язык XSLT обладает широким набором возможностей с большими возможностями и обеспечивает гибкость применения. В него входит много функций, которые полезны, но могут злонамеренно использоваться внешними источниками. Чтобы использовать XSLT безопасно, необходимо иметь представление о проблемах безопасности, сопряженных с использованием XSLT, и основных стратегиях, применяемых для снижения этих рисков.  
  
## <a name="xslt-extensions"></a>Расширения XSLT  
 Двумя популярными расширениями XSLT являются скрипты в таблице стилей и объекты расширения. Эти расширения позволяют процессору XSLT выполнять программный код.  
  
-   Объекты расширения добавляют возможности программирования к преобразованиям XSL.  
  
-   Можно внедрять скрипты в таблицу стилей с помощью элемента расширения `msxsl:script`.  
  
### <a name="extension-objects"></a>Объекты расширения  
 Расширяемые объекты добавляются с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>. Для поддержки расширяемых объектов необходим набор разрешений FullTrust. Это гарантирует, что во время выполнения кода из расширяемого объекта не произойдет повышение разрешений. Попытка вызова метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> при отсутствии разрешений FullTrust приведет к исключению безопасности.  
  
### <a name="style-sheet-scripts"></a>Скрипты в таблицах стилей  
 Можно внедрять скрипты в таблицу стилей с помощью расширяемого элемента `msxsl:script`. Поддержка скриптов является дополнительной функцией класса <xref:System.Xml.Xsl.XslCompiledTransform>, которая по умолчанию отключена. Чтобы включить скрипты, установите свойство <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A?displayProperty=nameWithType> в значение `true` и передайте объект <xref:System.Xml.Xsl.XsltSettings> методу <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  
  
#### <a name="guidelines"></a>Рекомендации  
 Включайте скрипты только в том случае, если таблица стилей получена из доверенного источника. Если нельзя проверить источник таблицы стилей или таблица стилей получена из ненадежного источника, передайте значение `null` для аргумента параметров XSLT.  
  
## <a name="external-resources"></a>Внешние ресурсы  
 Язык XSLT обладает функциями, такими как `xsl:import`, `xsl:include` и `document()`, в которых процессору необходимо разрешать URI-ссылки. Класс <xref:System.Xml.XmlResolver> используется для разрешения внешних ресурсов. Внешние ресурсы может понадобиться разрешать в следующих двух случаях:  
  
-   если во время компиляции таблицы стилей для разрешения <xref:System.Xml.XmlResolver> и `xsl:import` используется объект `xsl:include`;  
  
-   если во время выполнения преобразования для разрешения функции <xref:System.Xml.XmlResolver> используется объект `document()`.  
  
    > [!NOTE]
    >  Функция `document()` по умолчанию отключена в классе <xref:System.Xml.Xsl.XslCompiledTransform>. Чтобы включить эту функцию, установите свойство <xref:System.Xml.Xsl.XsltSettings.EnableDocumentFunction%2A?displayProperty=nameWithType> в значение `true` и передайте объект <xref:System.Xml.Xsl.XsltSettings> методу <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  
  
 Методы <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> и <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> имеют перегруженные версии, принимающие объект <xref:System.Xml.XmlResolver> в качестве одного из аргументов. Если <xref:System.Xml.XmlResolver> не указан, используется <xref:System.Xml.XmlUrlResolver> по умолчанию без учетных данных.  
  
#### <a name="guidelines"></a>Рекомендации  
 Включайте функцию `document()` только в том случае, если таблица стилей получена из доверенного источника.  
  
 Следующий список описывает, когда может потребоваться указать объект <xref:System.Xml.XmlResolver>:  
  
-   Если процессу XSLT требуется доступ к сетевому ресурсу, требующему проверки подлинности, можно использовать <xref:System.Xml.XmlResolver> с необходимыми учетными данными.  
  
-   Если необходимо ограничить ресурсы, к которым имеет доступ процесс XSLT, можно использовать <xref:System.Xml.XmlSecureResolver> с надлежащим набором разрешений. Использовать класс <xref:System.Xml.XmlSecureResolver> рекомендуется, если вам необходимо открыть ресурс, которым вы не управляете или к которому нет доверия.  
  
-   Если необходимо настроить поведение особым образом, можно реализовать собственный класс <xref:System.Xml.XmlResolver> и использовать его для разрешения ресурсов.  
  
-   Если необходимо убедиться в отсутствии доступа к внешним ресурсам, можно указать `null` в качестве значения аргумента <xref:System.Xml.XmlResolver>.  
  
## <a name="see-also"></a>См. также

- [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)  
- [Разрешение внешних ресурсов в ходе обработки XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
- [Управление доступом для кода](https://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03)
