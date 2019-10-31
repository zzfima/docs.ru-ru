---
title: Практическое руководство. Создание класса с помощью CodeDOM
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Code Document Object Model, graphs
- Code Document Object Model, creating classes
- graphing with CodeDOM
- CodeDOM, creating classes
- CodeDOM, graphs
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
ms.openlocfilehash: ff7c9d1593c8e75f9bcaeda6577c7cb941719749
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130196"
---
# <a name="how-to-create-a-class-using-codedom"></a>Практическое руководство. Создание класса с помощью CodeDOM
В следующих процедурах демонстрируется создание и компиляция графа CodeDOM, который создает класс, содержащий два поля, три свойства, метод, конструктор и точку входа.  
  
1. Создайте приложение консоли, которое будет использовать код CodeDOM для создания исходного кода класса.  
  
     В этом примере создающий класс называется `Sample`, а созданный код — это класс `CodeDOMCreatedClass` в файле с именем SampleCode.  
  
2. В создающем классе инициализируйте граф CodeDOM и используйте методы CodeDOM для определения элементов, конструктора и точки входа (метод `Main`) созданного класса.  
  
     В этом примере созданный класс имеет два поля, три свойства, конструктор, метод и метод `Main`.  
  
3. В создающем классе создайте поставщик кода определенного языка и вызовите его метод <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> для создания кода из графа.  
  
4. Скомпилируйте и выполните приложение для создания кода.  
  
     В этом примере созданный код находится в файле с именем SampleCode. Скомпилируйте и выполните этот код для просмотра выходных данных примера.  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a>Создание приложения, которое будет выполнять код CodeDOM  
  
- Создайте класс приложения консоли для включения кода CodeDOM. Определите глобальные поля, которые должны использоваться в классе для ссылки на сборку (<xref:System.CodeDom.CodeCompileUnit>) и класс (<xref:System.CodeDom.CodeTypeDeclaration>), укажите имя созданного исходного файла и объявите метод `Main`.  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### <a name="to-initialize-the-codedom-graph"></a>Инициализация графа CodeDOM  
  
- В конструкторе для класса приложения консоли инициализируйте сборку и класс, затем добавьте соответствующие объявления в граф CodeDOM.  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### <a name="to-add-members-to-the-codedom-graph"></a>Добавление элементов в граф CodeDOM  
  
- Добавьте поля в граф CodeDOM, добавив объекты <xref:System.CodeDom.CodeMemberField> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
- Добавьте свойства в граф CodeDOM, добавив объекты <xref:System.CodeDom.CodeMemberProperty> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
- Добавьте метод в граф CodeDOM, добавив объект <xref:System.CodeDom.CodeMemberMethod> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
- Добавьте конструктор в граф CodeDOM, добавив объект <xref:System.CodeDom.CodeConstructor> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
- Добавьте точку входа вграф CodeDOM, добавив объект <xref:System.CodeDom.CodeEntryPointMethod> в свойство <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> класса.  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a>Создание кода из графа CodeDOM  
  
- Создайте исходный код из графа CodeDOM, вызвав метод <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>.  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### <a name="to-create-the-graph-and-generate-the-code"></a>Создание графа и генерация кода  
  
1. Добавьте методы, созданные на предыдущих этапах, в метод `Main`, определенный на первом этапе.  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2. Скомпилируйте и выполните создающий класс.  
  
## <a name="example"></a>Пример  
 В следующем примере кода представлен код, созданный на предыдущих этапах.  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 При компиляции и выполнении предыдущего примера, происходит создание следующего исходного кода.  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 Созданный исходный код формирует следующие выходные данные при компиляции и выполнении.  
  
```output
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Для выполнения этого кода должно быть установлено разрешение `FullTrust`.  
  
## <a name="see-also"></a>См. также

- [Использование CodeDOM](using-the-codedom.md)
- [Создание и компиляция исходного кода из графа CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md)
