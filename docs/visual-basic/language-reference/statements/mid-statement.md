---
title: "Оператор Mid | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.MidB"
  - "vb.Mid"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Mid - оператор"
  - "строки [Visual Basic], замена"
  - "строки [Visual Basic], подстроки"
  - "подстроки, Mid - оператор"
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Оператор Mid
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Заменяет указанное число знаков в переменной типа `String` знаками из другой строки.  
  
## Синтаксис  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## Части  
 `Target`  
 Обязательный.  Имя переменной типа `String` для изменения.  
  
 `Start`  
 Обязательный.  Выражение типа `Integer`.  Положение символа в `Target`, где начинается замена текста.  `Start` нижняя граница индекса равна единице.  
  
 `Length`  
 Необязательный.  Выражение типа `Integer`.  Число заменяемых знаков.  Если параметр опущен, используется вся строка `String`.  
  
 `StringExpression`  
 Обязательный.  Выражение `String`, заменяющее часть строки `Target`.  
  
## Исключения  
  
|Тип исключения|Атрибут Condition|  
|--------------------|-----------------------|  
|<xref:System.ArgumentException>|Значение параметра `Start` \<\= 0 или `Length` \< 0.|  
  
## Заметки  
 Число заменяемых знаков всегда меньше или равно числу знаков в `Target`.  
  
 Visual Basic имеет функцию <xref:Microsoft.VisualBasic.Strings.Mid%2A> и оператор `Mid`.  Оба этих элемента влияют на указанное число знаков в строке, но функция `Mid` возвращает знаки, в то время как оператор `Mid` заменяет символы.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  В предыдущих версиях Visual Basic оператор `MidB` заменяет подстроку в байтах, а не в знаках.  В основном она применяется для преобразования строк в приложениях с двухбайтовым набором знаков \(DBCS\).  Все строки Visual Basic .NET кодируются в Юникоде. `MidB` не поддерживается.  
  
## Пример  
 В данном примере оператор `Mid` используется для замены указанного числа знаков строковой переменной на знаки из другой строки.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/mid-statement_1.vb)]  
  
## Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:** `Strings`  
  
 **Сборка:** [!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime-md.md)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 [Строки](../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Знакомство со строками в Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)