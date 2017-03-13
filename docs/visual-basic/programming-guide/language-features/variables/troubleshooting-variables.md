---
title: "Устранение неполадок, связанных с переменными, в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "устранение неполадок [Visual Basic], переменные"
  - "переменные [Visual Basic], устранение неполадок"
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Устранение неполадок, связанных с переменными, в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

На этой странице приведены некоторые общие проблемы, которые могут возникнуть при работе с переменными в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Не удается получить доступ к членам объекта  
 Если ваш код пытается получить доступ к свойству или методу объекта, могут возникнуть две следующие ошибки.  
  
-   Компилятор может создать сообщение об ошибке, если вы объявляете переменную объекта с определенным типом и затем ссылаетесь на член, не определенный этим типом.  
  
-   <xref:System.MemberAccessException> времени выполнения возникает, когда объект, присвоенный переменной объекта, не является элементом, доступ к которому пытается получить код. В случае с переменной [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) это исключение также возникает, если член не является `Public`. Это происходит потому, что позднее связывание разрешает доступ только к членам `Public`.  
  
 Когда [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) задает для проверки типа значение `On`, переменная объекта может получать доступ только к методам и свойствам класса, в котором она объявлена. Это показано в следующем примере.  
  
 [!CODE [VbVbalrStatements#49](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#49)]  
  
 [!code-vb[VbVbalrVariables#2](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/troubleshooting-variables_1.vb)]  
  
 В этом примере `p` может использовать только члены класса <xref:System.Object> без свойства `Left`. С другой стороны, `q` был объявлен с типом <xref:System.Windows.Forms.Label>, поэтому он может использовать все методы и свойства класса <xref:System.Windows.Forms.Label> в пространстве имен <xref:System.Windows.Forms>.  
  
### Правильный подход  
 Чтобы иметь возможность доступа ко всем членам объекта определенного класса, объявите переменную объекта с типом этого класса, если это возможно. В противном случае, например если вы не знаете тип объекта во время компиляции, необходимо задать `Option Strict` значение `Off` и объявить переменную с типом [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md). В этом случае переменной могут быть присвоены объекты любого типа, а вы должны выполнить действия, чтобы убедиться, что текущий назначенный объект имеет допустимый тип. Для этого можно воспользоваться [Оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## Другие компоненты не могут получить доступ к переменной  
 В именах [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]*регистр не учитывается*. Если два имени отличаются только регистром букв, компилятор интерпретирует их как одно и то же. Например, он считает, что `ABC` и `abc` являются одним и тем же объявленным элементом.  
  
 Однако среда CLR использует привязку *с учетом регистра*. Таким образом, при создании сборки или DLL и предоставлении к ней доступа другим сборкам, в именах регистр учитываться не будет. Например, если определен класс с элементом `ABC` и другие сборки используют класс с помощью среды CLR, они должны ссылаться на элемент как на `ABC`. Если впоследствии вы перекомпилируете класс и измените имя элемента на `abc`, другие сборки, использующие класс, больше не смогут обращаться к этому элементу. Таким образом, при выпуске обновленной версии сборки нельзя изменять регистр имен открытых элементов.  
  
 Для получения дополнительной информации см. [Среда CLR](../Topic/Common%20Language%20Runtime%20\(CLR\).md).  
  
### Правильный подход  
 Чтобы другие компоненты получали доступ к переменным, рассматривайте их имена так, как если бы в них учитывался регистр. При тестировании класса или модуля убедитесь, что другие сборки выполняют привязку к нужным переменным. После публикации компонента не изменяйте существующие имена переменных и их регистр.  
  
## Используется неправильная переменная  
 При наличии нескольких переменных с одинаковыми именами компилятор [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] пытается разрешить каждую ссылку на это имя. Если переменные имеют различные области действия, компилятор разрешает ссылку на объявление с самой узкой областью. Если они имеют одну и ту же область действия, разрешение не выполняется и компилятор сообщает об ошибке. Для получения дополнительной информации см. [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
### Правильный подход  
 Избегайте использования переменных с одинаковыми именами, но разными областями действия. При работе с другими сборками или проектами избегайте использования любых имен, определенных в их внешних компонентах, насколько это возможно. При наличии нескольких переменных с одним и тем же именем необходимо уточнить каждую ссылку на такую переменную. Дополнительные сведения см. в разделе [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## См. также  
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Объявление переменных объектов](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Практическое руководство. Доступ к членам объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Практическое руководство. Определение типа, на который указывает объектная переменная](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)