---
title: "Объекты расширения XSLT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 18106b74c19ffdfc33176a12bec07daf2b19b17e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="xslt-extension-objects"></a>Объекты расширения XSLT
Объекты расширения используются для расширения функциональности таблиц стилей. Объекты расширения обслуживаются классом <xref:System.Xml.Xsl.XsltArgumentList>.  
  
 Далее приведены преимущества использования объекта расширения в сравнении с внедренными скриптами.  
  
-   Обеспечивает улучшенную инкапсуляцию и повторное использование классов.  
  
-   Уменьшает размер и улучшает обслуживание таблиц стилей.  
  
 Объекты расширения XSLT добавляются в объект <xref:System.Xml.Xsl.XsltArgumentList> с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>. В это время с объектом расширения связываются полное имя и URI-код пространства имен.  
  
> [!NOTE]
>  Чтобы вызвать метод <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>, необходим набор разрешений FullTrust. См. дополнительные сведения о [защите доступа к коду](http://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03) и [именованных наборов разрешений (NIB)](http://msdn.microsoft.com/library/08250d67-c99d-4ab0-8d2b-b0e12019f6e3).  
  
 Объекты расширения возвращают один из четырех базовых типов данных XPath: `number`, `string`, `Boolean` и `node set`.  
  
 Любой метод, который определен с ключевым словом `params`, позволяющим передавать точно не установленное количество параметров, в настоящее время не поддерживается классом <xref:System.Xml.Xsl.XslCompiledTransform>. Таблицы стилей XSLT, которые используют любой метод, определенный с ключевым словом `params`, не будут работать правильно. Дополнительные сведения см. в руководстве по [params](~/docs/csharp/language-reference/keywords/params.md).  
  
### <a name="to-use-an-xslt-extension-object"></a>Использование объекта расширения XSLT  
  
1.  Создайте объект <xref:System.Xml.Xsl.XsltArgumentList> и добавьте объект расширения с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.  
  
2.  Вызовите объект расширения из таблицы стилей.  
  
3.  Передайте объект <xref:System.Xml.Xsl.XsltArgumentList> методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## <a name="see-also"></a>См. также  
 [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)  
 [Рекомендации по безопасности XSLT](../../../../docs/standard/data/xml/xslt-security-considerations.md)
