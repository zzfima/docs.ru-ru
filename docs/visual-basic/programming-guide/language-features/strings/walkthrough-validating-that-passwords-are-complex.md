---
title: "Проверка сложности паролей (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- String data type, validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e899900d60bddb83fb640abcc7f11f333c1af870
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Пошаговое руководство. Проверка паролей на сложность (Visual Basic)
Этот метод проверяет некоторые характеристики строгого пароля и обновляет строковый параметр сведениями о том, какие проверки пароля завершается ошибкой.  
  
 Пароли могут использоваться в системе безопасности для авторизации пользователя. Однако пароли должны быть сложными для взлома. Злоумышленники могут использовать *словарная атака* программу, которая перебирает все слова в словаре (или нескольких словарей на разных языках) и проверяет, является ли работать любое из слов в качестве пароля пользователя. Можно быстро подобрать слабые пароли, такие как «Yankees» или «Mustang». Более надежные пароли, такие как «? Вы «L1N3vaFiNdMeyeP@sSWerd!», гораздо реже подобрать. Система защиты паролей необходимо убедиться, чтобы пользователи выбирали надежные пароли.  
  
 Надежный пароль является сложным (содержащим сочетание верхнего, нижнего регистра, цифры и специальные символы) и не является словом. В этом примере демонстрируется проверка сложности.  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
 [!code-vb[VbVbcnRegEx&#1;](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Этот метод путем передачи строки, содержащей этот пароль.  
  
 Для этого примера требуются:  
  
-   Доступ к членам <xref:System.Text.RegularExpressions>имен.</xref:System.Text.RegularExpressions> Добавление `Imports` инструкции, если в коде не используются полностью квалифицированные имена элементов. Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Безопасность  
 При перемещении пароля по сети необходимо использовать безопасный метод передачи данных. Дополнительные сведения см. в разделе [безопасности веб-приложений ASP.NET](https://msdn.microsoft.com/library/330a99hc).  
  
 Можно улучшить точность `ValidatePassword` функцию, добавив дополнительные проверки сложности:  
  
-   Сравните пароль и его подстроки от имени пользователя, идентификатор пользователя и словарем определяемые приложением. Кроме того рассматривать визуальный вид символов как эквивалент при выполнении сравнений. Например рассматривать буквы «l» и «e» как эквиваленты цифр «1» и «3».  
  
-   Если имеется только один символ верхнего регистра, убедитесь, что это не первый знак пароля пользователя.  
  
-   Убедитесь, что последние два символа пароля — буквы.  
  
-   Не разрешать пароли, в которых все символы введены из верхнего ряда клавиатуры.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Text.RegularExpressions.Regex></xref:System.Text.RegularExpressions.Regex>   
 [Безопасность веб-приложений ASP.NET](https://msdn.microsoft.com/library/330a99hc)
