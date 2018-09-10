---
title: volatile (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: be7e081b18702710c00b5b86a9bc152800f0cf3d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526223"
---
# <a name="volatile-c-reference"></a>volatile (Справочник по C#)
Ключевое слово `volatile` означает, что поле может изменить несколько потоков, выполняемых одновременно. Поля, объявленные `volatile`, не участвуют в оптимизации компилятора, предполагающей доступ для одного потока. Эти ограничения гарантируют, что все потоки будут видеть временные записи, выполняемые другим потоком, в порядке выполнения. Нет никакой гарантии единого общего прядка временных записей во всех потоках выполнения.  
  
 Обычно модификатор `volatile` используется для поля, к которому обращаются несколько потоков; при этом для сериализации доступа оператор [lock](../../../csharp/language-reference/keywords/lock-statement.md) не применяется.  
  
 Ключевое слово `volatile` может применяться к полям следующих типов:  
  
-   Ссылочные типы.  
  
-   Типы указателей (в небезопасном контексте). Несмотря на то, что сам указатель может быть изменяемым, объект, на который он указывает, должен быть постоянным. Другими словами, объявить указатель на изменяемый объект невозможно.  
  
-   Типы: sbyte, byte, short, ushort, int, uint, char, float и bool.  
  
-   Тип перечисления с одним из следующих базовых типов: byte, sbyte, short, ushort, int или uint.  
  
-   Параметры универсального типа называются ссылочными типами.  
  
-   <xref:System.IntPtr> и <xref:System.UIntPtr>.  
  
 Ключевое слово volatile можно применять только к полям класса или структуры. Локальные переменные не могут объявляться как `volatile`.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как объявить переменную поля открытого типа `volatile`.  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание вспомогательного или рабочего потока и его применение для выполнения обработки параллельно с обработкой основного потока. Дополнительные сведения о многопоточности см. в разделах [Управляемая поточность](../../../standard/threading/index.md) и [Работа с потоками (C#)](../../programming-guide/concepts/threading/index.md).  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
- [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)
