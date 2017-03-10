---
title: "&lt;подписьПроцедуры1&gt; несовместима с CLS, поскольку перегружает &lt;подписьПроцедуры2&gt;, отличающуюся только массивом типов параметров или его рангом | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40035"
  - "bc40035"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40035"
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &lt;подписьПроцедуры1&gt; несовместима с CLS, поскольку перегружает &lt;подписьПроцедуры2&gt;, отличающуюся только массивом типов параметров или его рангом
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Процедура или свойство помечено как `<CLSCompliant(True)>`, когда оно переопределяет другую процедуру или свойство, единственное отличие между списками их параметров — вложенный уровень массива массивов или ранг массива.  
  
 В следующих объявлениях второе и третье объявления создают эту ошибку.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 Второе объявление изменяет исходный одномерный параметр `arrayParam` на массив массивов.  Третье объявление превращает `arrayParam` в двухмерный массив \(ранг 2\).  Поскольку Visual Basic допускает перегрузки, поддерживающие только одно из этих изменений, такая перегрузка несовместима с [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\).  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу параметру атрибута `isCompliant` присваивается значение `True` или `False`, указывающее на совместимость или несовместимость.  Значение по умолчанию для этого параметра отсутствует, поэтому значение необходимо указать.  
  
 Если к элементу не применяется атрибут <xref:System.CLSCompliantAttribute>, элемент считается несовместимым.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40035  
  
### Чтобы исправить эту ошибку  
  
-   Если требуется CLS\-совместимость, определите перегрузки, отличающиеся друг от друга по большему количеству признаков, чем представлено на этой странице справки.  
  
-   Если требуется, чтобы перегрузки отличались только по признакам, описанным на этой странице справки, удалите <xref:System.CLSCompliantAttribute> из их определения или пометьте их как `<CLSCompliant(False)>`.  
  
## См. также  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)   
 [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)