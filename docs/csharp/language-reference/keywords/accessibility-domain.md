---
title: Область доступности (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 20489f399dd2baa9c30c7277adc9fe4b7e7fce19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="accessibility-domain-c-reference"></a>Область доступности (Справочник по C#)
Область доступности члена определяет, в каких разделах программы может присутствовать ссылка на этот член. Если член вложен в другой тип, его область доступности определяется как [уровнем доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) самого члена, так и областью доступности типа, непосредственно содержащего вложенный тип.  
  
 Область доступности типа верхнего уровня — это по крайней мере текст программы проекта, в котором он объявлен. То есть область включает в себя все исходные файлы данного проекта. Область доступности вложенного типа — это по крайней мере текст программы типа, в котором он объявлен. Таким образом, областью является тело типа, включающее все вложенные типы. Область доступности вложенного типа никогда не выходит за пределы области доступности содержащего его типа. Эти принципы продемонстрированы в приведенном ниже примере.  
  
## <a name="example"></a>Пример  
 Этот пример содержит тип верхнего уровня `T1` и два вложенных класса: `M1` и `M2`. Классы содержат поля, имеющие различную объявленную доступность. В методе `Main` после каждого оператора следует комментарий, указывающий область доступности для каждого члена. Обратите внимание, что операторы, ссылающиеся на недоступные члены, закомментированы. Если необходимо просмотреть сообщения об ошибках, выдаваемые компилятором при попытке обращения к недоступному члену, удаляйте комментарии по одному.  
  
 [!code-csharp[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [Ограничения на использование уровней доступности](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [public](../../../csharp/language-reference/keywords/public.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)
