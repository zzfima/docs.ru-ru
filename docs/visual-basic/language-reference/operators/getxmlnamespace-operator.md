---
title: Оператор GetXmlNamespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: bfccdcd9b5d35418b206dfa9fefffb5ddab69c66
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592169"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>Оператор GetXmlNamespace (Visual Basic)
Возвращает объект <xref:System.Xml.Linq.XNamespace>, соответствующий указанному префиксу пространства имен XML.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Части  
 `xmlNamespacePrefix`  
 Необязательно. Строка, определяющая префикс пространства имен XML. Если указано, эта строка должна быть допустимым идентификатором XML. Дополнительные сведения см. в разделе [Имена объявленных XML-элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Если префикс не указан, возвращается пространство имен по умолчанию. Если пространство имен по умолчанию не указано, возвращается пустое пространство имен.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XNamespace>, соответствующий префиксу пространства имен XML.  
  
## <a name="remarks"></a>Примечания  
 Оператор `GetXmlNamespace` получает объект <xref:System.Xml.Linq.XNamespace>, соответствующий префиксу пространства имен XML `xmlNamespacePrefix`.  
  
 Префиксы пространства имен XML можно использовать непосредственно в XML-литералах и свойствах осей XML. Однако необходимо использовать оператор `GetXmlNamespace` для преобразования префикса пространства имен в объект <xref:System.Xml.Linq.XNamespace>, прежде чем его можно будет использовать в коде. Можно добавить неполное имя элемента в <xref:System.Xml.Linq.XNamespace> объект, чтобы получить полный <xref:System.Xml.Linq.XName> объект, который требуется многим [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] методам.  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется импорт `ns` как префикса пространства имен XML. Затем он использует префикс пространства имен для создания XML-литерала и доступа к первому дочернему узлу с полным именем `ns:phone`. Затем этот дочерний узел передается в подпрограммы `ShowName`, которая формирует полное имя с помощью оператора `GetXmlNamespace`. Затем `ShowName` подпрограммы передает полное имя методу <xref:System.Xml.Linq.XNode.Ancestors%2A>, чтобы получить родительский узел `ns:contact`.  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 При вызове `TestGetXmlNamespace.RunSample()`отображается окно сообщения, содержащее следующий текст:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>См. также:

- [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [Доступ к XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
