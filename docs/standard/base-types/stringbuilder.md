---
title: "Использование класса StringBuilder в .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Remove - метод"
  - "строки [платформа .NET Framework], емкости"
  - "StringBuilder - объект"
  - "Replace - метод"
  - "AppendFormat - метод"
  - "Append - метод"
  - "Insert - метод"
  - "строки [платформа .NET Framework], объект StringBuilder"
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Использование класса StringBuilder в .NET Framework
Объект <xref:System.String> является неизменяемым. Каждый раз при использовании одного из методов в классе <xref:System.String?displayProperty=fullName> вы создаете новый объект строки в памяти. При этом для нового объекта требуется новое выделение пространства. В тех случаях, когда необходимо выполнять повторяющиеся модификации строки, издержки, связанные с созданием нового объекта <xref:System.String>, могут оказаться значительными. Чтобы изменять строку без создания нового объекта, можно использовать класс <xref:System.Text.StringBuilder?displayProperty=fullName>. Например, использование класса <xref:System.Text.StringBuilder> может повысить производительность при соединении большого количества строк в цикле.  
  
## Импорт пространства имен System.Type  
 Класс <xref:System.Text.StringBuilder> находится в пространстве имен <xref:System.Text>.  Чтобы избежать необходимости предоставления полного имени типа в коде, вы можете импортировать пространство имен <xref:System.Text>:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## Создание экземпляров объекта StringBuilder  
 Вы можете создать новый экземпляр класса <xref:System.Text.StringBuilder> путем инициализации переменной с помощью одного из перегруженных методов конструктора, как показано в следующем примере.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## Настройка емкости и длины  
 Хотя <xref:System.Text.StringBuilder> является динамическим объектом, который позволяет вам развернуть ряд символов в строке, которые она инкапсулирует, вы можете указать максимальное число содержащихся в ней символов. Это значение называется емкостью объекта, и его не следует путать с длиной строки, которую содержит текущий <xref:System.Text.StringBuilder>. Например, вы можете создать новый экземпляр класса <xref:System.Text.StringBuilder> со строкой Hello, длина которой составляет 5 символов, или указать, что максимальная емкость объекта — 25. При изменении <xref:System.Text.StringBuilder> размер не перераспределяется, пока не будет достигнута граница емкости. Когда это происходит, новое пространство выделяется автоматически, а емкость удваивается. Вы можете указать емкость класса <xref:System.Text.StringBuilder> с помощью одного из перегруженных конструкторов. В следующем примере показано, что объект `MyStringBuilder` можно развернуть максимум на 25 позиций.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Кроме того, вы можете использовать свойство <xref:System.Text.StringBuilder.Capacity%2A> для чтения или записи, чтобы задать максимальную длину объекта. В следующем примере используется свойство **Capacity** для определения максимальной длины объекта.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 Метод <xref:System.Text.StringBuilder.EnsureCapacity%2A> можно использовать для проверки емкости текущего **StringBuilder**. Если емкость больше переданного значения, изменения не вносятся; однако если емкость меньше переданного значения, текущая емкость изменяется для соответствия переданному значению.  
  
 Можно также просмотреть или задать свойство <xref:System.Text.StringBuilder.Length%2A>. Если вы задали для свойства **Length** значение больше значения свойства **Capacity**, значение свойства **Capacity** будет автоматически изменено на то же самое значение, что и у свойства **Length**. Если задать для свойства **Length** значение меньше длины строки в текущем **StringBuilder**, строка будет укорочена.  
  
## Изменение строки StringBuilder  
 В следующей таблице перечислены методы, которые можно использовать для изменения содержимого **StringBuilder**.  
  
|Имя метода|Применение|  
|----------------|----------------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>|Добавляет сведения в конец текущего **StringBuilder**.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=fullName>|Заменяет отформатированным текстом описатель формата, переданный в строке.|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=fullName>|Вставляет строку или объект в указанный индекс текущего **StringBuilder**.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=fullName>|Удаляет указанное количество символов из текущего **StringBuilder**.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=fullName>|Заменяет указанный символ в указанном индексе.|  
  
### Добавить  
 Метод **Append** можно использовать для добавления текста или представления строки объекта к концу строки, представленной текущим **StringBuilder**. Следующий пример инициализирует **StringBuilder** с текстом Hello World, а затем добавляет текст в конец объекта. Пространство выделяется автоматически при необходимости.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### AppendFormat  
 Метод <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=fullName> добавляет текст в конец объекта <xref:System.Text.StringBuilder>. Он поддерживает функцию составного форматирования \(дополнительные сведения см. в разделе [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md)\) путем вызова реализации <xref:System.IFormattable> форматируемого объекта или объектов. Следовательно, он принимает строки стандартного формата для числовых значений, значений даты и времени, значений перечисления, строки пользовательского формата для чисел и дат и строки формата, определенные для пользовательских типов. \(Дополнительные сведения о форматировании см. в разделе [Типы форматирования](../../../docs/standard/base-types/formatting-types.md).\) Вы можете использовать этот метод для настройки формата переменных и добавления этих значений в <xref:System.Text.StringBuilder>. В следующем примере используется метод <xref:System.Text.StringBuilder.AppendFormat%2A> для размещения целочисленного значения, отформатированного в качестве значения валюты в конце объекта <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### Insert  
 Метод <xref:System.Text.StringBuilder.Insert%2A> добавляет строку или объект в указанную позицию в текущем объекте <xref:System.Text.StringBuilder>. В следующем примере этот метод используется для вставки слова в шестую позицию объекта <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### Удалить  
 Вы можете использовать метод **Remove**, чтобы удалить указанное количество символов из текущего объекта <xref:System.Text.StringBuilder>, начиная с указанного индекса \(с отсчетом с нуля\). В следующем примере используется метод **Remove** для сокращения объекта <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### Заменить  
 Метод **Replace** можно использовать для замены символов в объекте <xref:System.Text.StringBuilder> другими указанными символами. В следующем примере метод **Replace** используется для поиска объекта <xref:System.Text.StringBuilder> для всех экземпляров восклицательного знака \(\!\) и замены их знаком вопроса \(?\).  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## Преобразование объекта StringBuilder в строку  
 Необходимо преобразовать объект <xref:System.Text.StringBuilder> в <xref:System.String> перед тем, как вы сможете передать строку, представленную объектом <xref:System.Text.StringBuilder>, методу, который содержит параметр <xref:System.String>, или отобразить ее в пользовательском интерфейсе. Это преобразование можно выполнить, вызвав метод <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName>. Следующий пример вызывает ряд методов <xref:System.Text.StringBuilder>, а затем вызывает метод <xref:System.Text.StringBuilder.ToString?displayProperty=fullName> для отображения строки.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## См. также  
 <xref:System.Text.StringBuilder?displayProperty=fullName>   
 [Основные операции со строками](../../../docs/standard/base-types/basic-string-operations.md)   
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)