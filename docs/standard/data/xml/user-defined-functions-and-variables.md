---
title: Определяемые пользователем функции и переменные
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 4772f20e-1e7f-496e-93c2-1484473be555
ms.openlocfilehash: 7040c2ccf6e3bfc6efcbec3505c633c6c3c6508f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710067"
---
# <a name="user-defined-functions-and-variables"></a>Определяемые пользователем функции и переменные
Класс <xref:System.Xml.XPath.XPathNavigator> содержит ряд методов, используемых для взаимодействия с данными <xref:System.Xml.XPath.XPathDocument>. Можно дополнить стандартные функции XPath, реализовав функции и переменные расширения для использования в выражениях запросов XPath. Метод <xref:System.Xml.XPath.XPathExpression.SetContext%2A> может принимать определяемый пользователем контекст, производный от <xref:System.Xml.Xsl.XsltContext>. Определяемые пользователем функции разрешаются в пользовательском контексте.  
  
 Функции и переменные расширения полезны для предотвращения атак путем внедрения XML-кода. В таких сценариях вводимые пользователем данные помещаются в пользовательские переменные и обрабатываются функциями расширения, в отличие от исходных данных, объединяемых с инструкциями по обработке. Функции и переменные расширения хранят вводимые пользователем данные, чтобы они работали с XML-данными только так, как планировалось разработчиком.  
  
 Для использования расширений реализуется пользовательский класс <xref:System.Xml.Xsl.XsltContext> вместе с интерфейсами <xref:System.Xml.Xsl.IXsltContextFunction> и <xref:System.Xml.Xsl.IXsltContextVariable>, которые поддерживают функции и переменные расширения. Объект <xref:System.Xml.XPath.XPathExpression> добавляет вводимые пользователем данные вместе со списком <xref:System.Xml.Xsl.XsltArgumentList> к пользовательскому объекту <xref:System.Xml.Xsl.XsltContext>.  
  
 Объект <xref:System.Xml.XPath.XPathExpression> представляет скомпилированный запрос, с помощью которого <xref:System.Xml.XPath.XPathNavigator> выполняет поиск и обработку узлов, определяемых выражением.  
  
 В следующем примере показана реализация пользовательского класса контекста, производного от <xref:System.Xml.Xsl.XsltContext>. В комментариях к коду описываются члены класса и их использование в пользовательских функциях. За этим сегментом кода следуют реализации функций и переменных, а также пример приложения, в котором используются эти реализации.  
  
 [!code-csharp[XPathExtensionFunctions#2](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#2)]
 [!code-vb[XPathExtensionFunctions#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#2)]  
  
 В следующем коде реализуется функция <xref:System.Xml.Xsl.IXsltContextFunction>. Класс, в котором реализуется <xref:System.Xml.Xsl.IXsltContextFunction>, разрешает и выполняет определяемые пользователем функции. В этом примере используется функция, определяемая объявлением `private int CountChar(string title, char charTocount)`.  
  
 В комментариях к коду описываются члены класса.  
  
 [!code-csharp[XPathExtensionFunctions#3](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#3)]
 [!code-vb[XPathExtensionFunctions#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#3)]  
  
 В следующем коде реализуется функция <xref:System.Xml.Xsl.IXsltContextVariable>. Этот класс разрешает ссылки на определяемые пользователем переменные в выражениях запросов XPath во время выполнения. Экземпляр этого класса создается и возвращается переопределенным методом <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A> пользовательского класса <xref:System.Xml.Xsl.XsltContext>.  
  
 В комментариях к коду описываются члены класса.  
  
 [!code-csharp[XPathExtensionFunctions#4](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#4)]
 [!code-vb[XPathExtensionFunctions#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#4)]  
  
 В области предыдущих определений классов следующий код использует пользовательскую функцию для подсчета символов в элементах документа `Tasks.xml`. В комментариях к коду описывается код, который компилирует пользовательскую функцию и выполняет ее в документе `Tasks.xml`.  
  
 [!code-csharp[XPathExtensionFunctions#1](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#1)]
 [!code-vb[XPathExtensionFunctions#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#1)]  
  
 В этом примере используются следующие XML-данные.  
  
 [!code-xml[XPathExtensionFunctions#5](../../../../samples/snippets/xml/VS_Snippets_Data/xpathextensionfunctions/XML/tasks.xml#5)]
