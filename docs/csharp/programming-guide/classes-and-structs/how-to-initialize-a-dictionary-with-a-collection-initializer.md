---
title: Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: ca2f508e5500cc135b2712362bcfb71778a664c1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45676562"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (Руководство по программированию на C#)

<xref:System.Collections.Generic.Dictionary%602> содержит коллекцию пар "ключ-значение". Ее метод <xref:System.Collections.Generic.Dictionary%602.Add*> принимает два параметра: один для ключа, другой — для значения. Для инициализации <xref:System.Collections.Generic.Dictionary%602> или любой коллекции, метод `Add` которой принимает несколько параметров, следует заключить каждый набор параметров в скобки, как показано в приведенном ниже примере.

## <a name="example"></a>Пример

В следующем примере кода <xref:System.Collections.Generic.Dictionary%602> инициализируется экземплярами типа `StudentName`.  
  
[!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]

Обратите внимание на две пары фигурных скобок в каждом элементе коллекции. Внутренняя пара фигурных скобок заключает инициализатор объекта `StudentName`, а внешняя пара — инициализатор пары "ключ – значение", которая будет добавлена в коллекцию `students` <xref:System.Collections.Generic.Dictionary%602>. И наконец, весь инициализатор коллекции для словаря заключается в фигурные скобки.

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, созданный в Visual Studio. По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] и содержит ссылку на библиотеку System.Core.dll и директиву using для пространства имен System.Linq. Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
