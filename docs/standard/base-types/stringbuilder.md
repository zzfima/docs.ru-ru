---
title: "Использование класса StringBuilder в .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3a6c8f6dee9f2a1da6ed4a8219c1b4832464d9aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-stringbuilder-class-in-net"></a>Использование класса StringBuilder в .NET
<xref:System.String> Является неизменяемым. Каждый раз при использовании одного из методов в <xref:System.String?displayProperty=nameWithType> класса, создании новый объект строки в памяти, в которой требуется новое выделение пространства для этого нового объекта. В ситуациях, когда необходимо выполнять повторяющиеся модификации строки, издержки, связанные с созданием нового <xref:System.String> объекта может требовать много ресурсов. <xref:System.Text.StringBuilder?displayProperty=nameWithType> Класс может использоваться для изменения строки без создания нового объекта. Например, с помощью <xref:System.Text.StringBuilder> класс может повысить производительность при соединении большого количества строк в цикле.  
  
## <a name="importing-the-systemtext-namespace"></a>Импорт пространства имен System.Text  
 <xref:System.Text.StringBuilder> Класса находится в <xref:System.Text> пространства имен.  Чтобы избежать необходимости предоставления полное имя типа в коде, можно импортировать <xref:System.Text> пространство имен:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>Создание экземпляров объекта StringBuilder  
 Можно создать новый экземпляр <xref:System.Text.StringBuilder> класса путем инициализации переменной с помощью одного из перегруженных методов конструктора, как показано в следующем примере.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>Настройка емкости и длины  
 Несмотря на то что <xref:System.Text.StringBuilder> является динамическим объектом, который позволяет расширить число символов в строке, которые она инкапсулирует, можно указать значение для максимального числа символов, содержащихся в ней. Это значение называется емкостью объекта и их не следует путать с длиной строки, текущий <xref:System.Text.StringBuilder> содержит. Например, можно создать новый экземпляр <xref:System.Text.StringBuilder> класса со строкой «Hello», который имеет длину 5, и может указать, что объект имеет максимальную емкость 25. При изменении <xref:System.Text.StringBuilder>, он не перераспределен размера пока не будет достигнута емкость. Когда это происходит, новое пространство выделяется автоматически, а емкость удваивается. Можно указать емкость этого <xref:System.Text.StringBuilder> класса с помощью одного из перегруженных конструкторов. В следующем примере показано, что объект `MyStringBuilder` можно развернуть максимум на 25 позиций.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Кроме того, можно использовать для чтения записи <xref:System.Text.StringBuilder.Capacity%2A> свойство, чтобы задать максимальную длину объекта. В следующем примере используется свойство **Capacity** для определения максимальной длины объекта.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 <xref:System.Text.StringBuilder.EnsureCapacity%2A> Метод может использоваться для проверки емкости текущего **StringBuilder**. Если емкость больше переданного значения, изменения не вносятся; однако если емкость меньше переданного значения, текущая емкость изменяется для соответствия переданному значению.  
  
 <xref:System.Text.StringBuilder.Length%2A> Свойства можно также просмотреть или задать. Если вы задали для свойства **Length** значение больше значения свойства **Capacity**, значение свойства **Capacity** будет автоматически изменено на то же самое значение, что и у свойства **Length**. Если задать для свойства **Length** значение меньше длины строки в текущем объекте **StringBuilder**, строка будет укорочена.  
  
## <a name="modifying-the-stringbuilder-string"></a>Изменение строки StringBuilder  
 В следующей таблице перечислены методы, которые можно использовать для изменения содержимого объекта **StringBuilder**.  
  
|Имя метода|Применение|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|Добавляет сведения в конец текущего объекта **StringBuilder**.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|Заменяет отформатированным текстом описатель формата, переданный в строке.|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|Вставляет строку или объект в указанный индекс текущего объекта **StringBuilder**.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|Удаляет указанное количество символов из текущего объекта **StringBuilder**.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|Заменяет указанный символ в указанном индексе.|  
  
### <a name="append"></a>Добавить  
 **Append** метод может использоваться для добавления текста или строкового представления объекта к концу строки, представленного текущим **StringBuilder**. Следующий пример инициализирует **StringBuilder** с текстом Hello World, а затем добавляет текст в конец объекта. Пространство выделяется автоматически при необходимости.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> Метод добавляет текст в конец <xref:System.Text.StringBuilder> объекта. Он поддерживает возможность составного форматирования (Дополнительные сведения см. в разделе [составное форматирование](../../../docs/standard/base-types/composite-formatting.md)) путем вызова <xref:System.IFormattable> реализацию объекта или объектов для форматирования. Следовательно, он принимает строки стандартного формата для числовых значений, значений даты и времени, значений перечисления, строки пользовательского формата для чисел и дат и строки формата, определенные для пользовательских типов. (Дополнительные сведения о форматировании см. в разделе [Типы форматирования](../../../docs/standard/base-types/formatting-types.md).) Этот метод можно использовать для настройки формата переменных и добавления этих значений <xref:System.Text.StringBuilder>. В следующем примере используется <xref:System.Text.StringBuilder.AppendFormat%2A> способ размещения целого числа в формате значения валюты в конце <xref:System.Text.StringBuilder> объекта.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>Insert  
 <xref:System.Text.StringBuilder.Insert%2A> Метод добавляет строку или объект в указанную позицию в текущем <xref:System.Text.StringBuilder> объекта. Следующий пример использует этот метод для вставки слова в шестую позицию объекта <xref:System.Text.StringBuilder> объекта.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>Удалить  
 Можно использовать **удалить** метод, чтобы удалить указанное количество символов из текущего <xref:System.Text.StringBuilder> объекта, начиная с указанного индекса (с нуля). В следующем примере используется **удалить** для сокращения <xref:System.Text.StringBuilder> объекта.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>Заменить  
 **Заменить** метод может использоваться для замены символов в <xref:System.Text.StringBuilder> объект с другой указанный символ. В следующем примере используется **заменить** метод для поиска <xref:System.Text.StringBuilder> объекта для всех экземпляров восклицательного знака (!) и замените их знак вопроса (?).  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>Преобразование объекта StringBuilder в строку  
 Необходимо преобразовать <xref:System.Text.StringBuilder> объект <xref:System.String> объекта, прежде чем можно передать строку, представленную <xref:System.Text.StringBuilder> объект для метода, имеющего <xref:System.String> параметр или его отображения в пользовательском интерфейсе. Это преобразование можно выполнить путем вызова <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> метод. Следующий пример вызывает ряд <xref:System.Text.StringBuilder> методы, а затем вызывает метод <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> метод для отображения строки.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Text.StringBuilder?displayProperty=nameWithType>  
 [Базовые операции со строками в .NET Framework](../../../docs/standard/base-types/basic-string-operations.md)  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)
