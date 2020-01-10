---
title: Разрешение внешних ресурсов в ходе обработки XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
ms.openlocfilehash: 58407d5f0c6e602af15f5b19b9a19cc6379b9af7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710288"
---
# <a name="resolving-external-resources-during-xslt-processing"></a>Разрешение внешних ресурсов в ходе обработки XSLT
Во время XSLT-преобразования может понадобиться несколько раз разрешать внешние ресурсы.  
  
## <a name="using-the-xmlresolver-class"></a>Использование класса XmlResolver  
 Класс <xref:System.Xml.XmlResolver> используется для разрешения внешних ресурсов. В следующей таблице описывается, когда класс <xref:System.Xml.XmlResolver> участвует в XSLT-обработке.  
  
|Задача XSLT|Зачем используется класс XmlResolver|  
|---------------|--------------------------------------|  
|Компиляция таблицы стилей|Разрешение URI таблицы стилей.<br /><br /> -и-<br /><br /> Разрешение URI-ссылок в любых элементах `xsl:import` или `xsl:include`.|  
|Выполнение таблицы стилей.|Разрешение URI документа контекста.<br /><br /> -и-<br /><br /> Разрешение URI-ссылок в любых функциях XSLT `document()`.|  
  
 Методы <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> и <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> включают в себя перегружаемые, принимающие объект <xref:System.Xml.XmlResolver> в качестве одного из аргументов. Если <xref:System.Xml.XmlResolver> не указан, используется <xref:System.Xml.XmlUrlResolver> по умолчанию без учетных данных.  
  
 Следующий список описывает, когда может потребоваться указать объект <xref:System.Xml.XmlResolver>:  
  
- Если процессу XSLT требуется доступ к сетевому ресурсу, требующему проверки подлинности, можно использовать <xref:System.Xml.XmlResolver> с необходимыми учетными данными.  
  
- Если необходимо ограничить ресурсы, к которым имеет доступ процесс XSLT, можно использовать <xref:System.Xml.XmlSecureResolver> с надлежащим набором разрешений. Использовать класс <xref:System.Xml.XmlSecureResolver> рекомендуется, если вам необходимо открыть ресурс, которым вы не управляете или к которому нет доверия.  
  
- Если необходимо настроить поведение особым образом, можно реализовать собственный класс <xref:System.Xml.XmlResolver> и использовать его для разрешения ресурсов.  
  
- Если необходимо убедиться в отсутствии доступа к внешним ресурсам, можно указать `null` в качестве значения аргумента <xref:System.Xml.XmlResolver>.  
  
## <a name="example"></a>Пример  
 В следующем примере компилируется таблица стилей, которая хранится на сетевом ресурсе. Объект <xref:System.Xml.XmlUrlResolver> задает учетные данные, необходимые для доступа к таблице стилей.  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.Xsl.XslCompiledTransform>
- <xref:System.Xml.Xsl.XsltSettings>
- [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
