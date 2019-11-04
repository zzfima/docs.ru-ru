---
title: Использование класса StringBuilder в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Remove method
- strings [.NET Framework], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET Framework], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
ms.openlocfilehash: 19ee90f3300e3b610eeefd4949baa2759b834a60
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121677"
---
# <a name="using-the-stringbuilder-class-in-net"></a>Использование класса StringBuilder в .NET
Объект <xref:System.String> является неизменяемым. Каждый раз при использовании одного из методов в классе <xref:System.String?displayProperty=nameWithType> вы создаете объект строки в памяти, для которого требуется выделение нового пространства. В случаях, когда необходимо выполнять повторяющиеся изменения строки, издержки, связанные с созданием объекта <xref:System.String>, могут оказаться значительными. Чтобы изменять строку без создания нового объекта, можно использовать класс <xref:System.Text.StringBuilder?displayProperty=nameWithType>. Например, использование класса <xref:System.Text.StringBuilder> может повысить производительность при соединении большого количества строк в цикле.  
  
## <a name="importing-the-systemtext-namespace"></a>Импорт пространства имен System.Text  
 Класс <xref:System.Text.StringBuilder> находится в пространстве имен <xref:System.Text>.  Чтобы не указывать в коде полное имя типа, вы можете импортировать пространство имен <xref:System.Text>:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>Создание экземпляров объекта StringBuilder  
 Вы можете создать экземпляр класса <xref:System.Text.StringBuilder> путем инициализации переменной с помощью одного из перегруженных методов конструктора, как показано в следующем примере.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>Настройка емкости и длины  
 Хотя <xref:System.Text.StringBuilder> является динамическим объектом, который позволяет вам развернуть ряд символов в строке, которые она инкапсулирует, вы можете указать максимальное число содержащихся в ней символов. Это значение называется емкостью объекта, и его не следует путать с длиной строки, которую содержит текущий объект <xref:System.Text.StringBuilder>. Например, вы можете создать экземпляр класса <xref:System.Text.StringBuilder> со строкой Hello, длина которой составляет 5 символов, указав при этом максимальную емкость объекта 25 символов. При изменении значения <xref:System.Text.StringBuilder> размер не перераспределяется, если не достигнута максимальная емкость. Когда это происходит, новое пространство выделяется автоматически, а емкость удваивается. Вы можете указать емкость класса <xref:System.Text.StringBuilder> с помощью одного из перегруженных конструкторов. В следующем примере показано, что объект `myStringBuilder` можно развернуть максимум на 25 позиций.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Кроме того, вы можете использовать доступное для чтения или записи свойство <xref:System.Text.StringBuilder.Capacity%2A>, чтобы задать максимальную длину объекта. В следующем примере используется свойство **Capacity** для определения максимальной длины объекта.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 Метод <xref:System.Text.StringBuilder.EnsureCapacity%2A> можно использовать для проверки емкости текущего объекта **StringBuilder**. Если емкость больше переданного значения, изменения не вносятся; однако если емкость меньше переданного значения, текущая емкость изменяется для соответствия переданному значению.  
  
 Можно также просмотреть или задать свойство <xref:System.Text.StringBuilder.Length%2A>. Если вы задали для свойства **Length** значение больше значения свойства **Capacity**, значение свойства **Capacity** будет автоматически изменено на то же самое значение, что и у свойства **Length**. Если задать для свойства **Length** значение меньше длины строки в текущем объекте **StringBuilder**, строка будет укорочена.  
  
## <a name="modifying-the-stringbuilder-string"></a>Изменение строки StringBuilder  
 В следующей таблице перечислены методы, которые можно использовать для изменения содержимого объекта **StringBuilder**.  
  
|Имя метода|Использовать|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|Добавляет сведения в конец текущего объекта **StringBuilder**.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|Заменяет отформатированным текстом описатель формата, переданный в строке.|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|Вставляет строку или объект в указанный индекс текущего объекта **StringBuilder**.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|Удаляет указанное количество символов из текущего объекта **StringBuilder**.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|Заменяет указанный символ в указанном индексе.|  
  
### <a name="append"></a>Добавить  
 Метод **Append** позволяет добавить текст или строковое представление объекта к концу строки, представленной текущим объектом **StringBuilder**. Следующий пример инициализирует **StringBuilder** с текстом Hello World, а затем добавляет текст в конец объекта. Пространство выделяется автоматически при необходимости.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 Метод <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> добавляет текс в конец объекта <xref:System.Text.StringBuilder>. Он поддерживает возможность составного форматирования (дополнительные сведения см. в статье [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md)) путем вызова реализации <xref:System.IFormattable> для одного или нескольких форматируемых объектов. Следовательно, он принимает строки стандартного формата для числовых значений, значений даты и времени, значений перечисления, строки пользовательского формата для чисел и дат и строки формата, определенные для пользовательских типов. (Дополнительные сведения о форматировании см. в разделе [Типы форматирования](../../../docs/standard/base-types/formatting-types.md).) Вы можете использовать этот метод для настройки формата переменных и добавления этих значений к <xref:System.Text.StringBuilder>. В следующем примере метод <xref:System.Text.StringBuilder.AppendFormat%2A> помещает в конец объекта <xref:System.Text.StringBuilder> целочисленное значение, отформатированное в виде значения валюты.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>Insert  
 Метод <xref:System.Text.StringBuilder.Insert%2A> добавляет строку или объект в указанную позицию в текущем объекте <xref:System.Text.StringBuilder>. В следующем примере этот метод вставляет слово в шестую позицию объекта <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>Удалить  
 Вы можете использовать метод **Remove**, чтобы удалить указанное количество символов из текущего объекта <xref:System.Text.StringBuilder>, начиная с указанного индекса (с отсчетом с нуля). В следующем примере метод **Remove** используется для сокращения объекта <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>Замените  
 Метод **Replace** можно использовать для замены символов в объекте <xref:System.Text.StringBuilder> другими указанными символами. В следующем примере метод **Replace** находит все экземпляры восклицательного знака (!) в объекте <xref:System.Text.StringBuilder> и заменяет их знаками вопроса (?).  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>Преобразование объекта StringBuilder в строку  
 Необходимо преобразовать объект <xref:System.Text.StringBuilder> в <xref:System.String>, прежде чем передавать представленную объектом <xref:System.Text.StringBuilder> строку методу, который содержит параметр <xref:System.String>, или вывести ее в пользовательском интерфейсе. Это преобразование можно выполнить, вызвав метод <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType>. Следующий пример вызывает несколько методов <xref:System.Text.StringBuilder>, а затем вызывает метод <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> для отображения строки.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- [Базовые операции со строками в .NET Framework](../../../docs/standard/base-types/basic-string-operations.md)
- [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)
