---
title: Руководство по программированию на C#. Объявление, создание экземпляра и использование делегата
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 7ac1d736e19c4dcf1c8408db944505c399762778
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712368"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a>Руководство по программированию на C#. Объявление, создание экземпляра и использование делегата
В C# 1.0 и более поздних версий делегаты можно объявлять так, как показано в следующем примере.  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 В C# 2.0 предоставлен более простой способ для записи предыдущего объявления, который показан в следующем примере.  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 В C# 2.0 и более поздних версиях можно использовать анонимный метод для объявления и инициализации [делегата](../../language-reference/builtin-types/reference-types.md), как показано в следующем примере.  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 В C# 3.0 и более поздних версиях можно объявлять делегаты и создавать для них экземпляры с помощью лямбда-выражения, как показано в следующем примере.  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 Дополнительные сведения см. в разделе [Лямбда-выражения](../statements-expressions-operators/lambda-expressions.md).  
  
 Следующий пример демонстрирует объявление, создание экземпляра и использование делегата. Класс `BookDB` инкапсулирует базу данных книжного магазина, в которой хранится информация о книгах. Он предоставляет метод `ProcessPaperbackBooks`, который находит в базе данных все книги в мягкой обложке и вызывает делегат для каждой из них. Используется тип `delegate` с именем `ProcessBookDelegate`. Класс `Test` использует этот класс для печати заголовков и средней цены книг в мягкой обложке.  
  
 Использование делегата помогает правильно разделить функции между базой данных книжного магазина и кодом клиента. Код клиента не имеет сведений о том, как хранятся книги и как код книжного магазина находит книги в мягкой обложке. Код книжного магазина не имеет сведений о том, какая обработка выполняется для найденных книг в мягкой обложке.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
- Объявление делегата.  
  
     Следующая инструкция объявляет новый тип делегата.  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     Каждый тип делегата описывает количество аргументов и их типы, а также тип возвращаемого значения для всех методов, которые он может инкапсулировать. Каждый раз, когда требуется новый набор типов аргументов или новый тип возвращаемого значения, нужно объявить новый тип делегата.  
  
- Создания экземпляра делегата.  
  
     После объявления типа делегата нужно создать объект этого делегата и связать его с определенным методом. Продолжая предыдущий пример, вы можете передать метод `PrintTitle` в метод `ProcessPaperbackBooks`, как показано в следующем примере:  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     Будет создан новый объект делегата, связанный со [статическим](../../language-reference/keywords/static.md) методом `Test.PrintTitle`. Аналогичным образом, в следующем примере передается нестатический метод `AddBookToTotal` для объекта `totaller`:  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     В обоих случаях новый объект делегата передается в метод `ProcessPaperbackBooks`.  
  
     После создания делегата невозможно изменить метод, с которым он связан. Объекты делегатов являются неизменяемыми.  
  
- Использование делегатов  
  
     Обычно после создания объекта делегата он передается в другой код, который будет использовать этот делегат. Для вызова объекта делегата используется имя этого объекта, за которым следуют параметризованные аргументы, которые нужно передать делегату. Ниже показан пример использования делегата.  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     Делегат можно вызвать синхронно, как показано в этом примере, или асинхронно при помощи методов `BeginInvoke` и `EndInvoke`.  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [События](../events/index.md)
- [Делегаты](./index.md)
