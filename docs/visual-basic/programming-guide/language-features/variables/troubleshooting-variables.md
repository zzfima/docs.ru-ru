---
title: Устранение неполадок, связанных с переменными
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
ms.openlocfilehash: 929540788e8134760446e02c3377e78d00ca17d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351776"
---
# <a name="troubleshooting-variables-in-visual-basic"></a>Устранение неполадок, связанных с переменными, в Visual Basic
This page lists some common problems that can occur when working with variables in Visual Basic.  
  
## <a name="unable-to-access-members-of-an-object"></a>Не удается получить доступ к членам объекта  
 Если ваш код пытается получить доступ к свойству или методу объекта, могут возникнуть две следующие ошибки.  
  
- Компилятор может создать сообщение об ошибке, если вы объявляете переменную объекта с определенным типом и затем ссылаетесь на член, не определенный этим типом.  
  
- <xref:System.MemberAccessException> времени выполнения возникает, когда объект, присвоенный переменной объекта, не является элементом, доступ к которому пытается получить код. В случае с переменной [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)это исключение также возникает, если член не является `Public`. Это происходит потому, что позднее связывание разрешает доступ только к членам `Public` .  
  
 Когда [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) задает для проверки типа значение `On`, переменная объекта может получать доступ только к методам и свойствам класса, в котором она объявлена. Это показано в следующем примере.  

 [!code-vb[VbVbalrVariables#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#2)]  
  
 В этом примере `p` может использовать только члены класса <xref:System.Object> без свойства `Left` . С другой стороны, `q` был объявлен с типом <xref:System.Windows.Forms.Label>, поэтому он может использовать все методы и свойства класса <xref:System.Windows.Forms.Label> в пространстве имен <xref:System.Windows.Forms> .  
  
### <a name="correct-approach"></a>Правильный подход  
 Чтобы иметь возможность доступа ко всем членам объекта определенного класса, объявите переменную объекта с типом этого класса, если это возможно. В противном случае, например если вы не знаете тип объекта во время компиляции, необходимо задать `Option Strict` значение `Off` и объявить переменную с типом [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md). В этом случае переменной могут быть присвоены объекты любого типа, а вы должны выполнить действия, чтобы убедиться, что текущий назначенный объект имеет допустимый тип. You can use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to make this determination.  
  
## <a name="other-components-cannot-access-your-variable"></a>Другие компоненты не могут получить доступ к переменной  
 Visual Basic names are *case-insensitive*. Если два имени отличаются только регистром букв, компилятор интерпретирует их как одно и то же. Например, он считает, что `ABC` и `abc` являются одним и тем же объявленным элементом.  
  
 Однако среда CLR использует привязку *с учетом регистра* . Таким образом, при создании сборки или DLL и предоставлении к ней доступа другим сборкам, в именах регистр учитываться не будет. Например, если определен класс с элементом `ABC`и другие сборки используют класс с помощью среды CLR, они должны ссылаться на элемент как на `ABC`. Если впоследствии вы перекомпилируете класс и измените имя элемента на `abc`, другие сборки, использующие класс, больше не смогут обращаться к этому элементу. Таким образом, при выпуске обновленной версии сборки нельзя изменять регистр имен открытых элементов.  
  
 Для получения дополнительной информации см. [Common Language Runtime](../../../../standard/clr.md).  
  
### <a name="correct-approach"></a>Правильный подход  
 Чтобы другие компоненты получали доступ к переменным, рассматривайте их имена так, как если бы в них учитывался регистр. При тестировании класса или модуля убедитесь, что другие сборки выполняют привязку к нужным переменным. После публикации компонента не изменяйте существующие имена переменных и их регистр.  
  
## <a name="wrong-variable-being-used"></a>Используется неправильная переменная  
 When you have more than one variable with the same name, the Visual Basic compiler attempts to resolve each reference to that name. Если переменные имеют различные области действия, компилятор разрешает ссылку на объявление с самой узкой областью. Если они имеют одну и ту же область действия, разрешение не выполняется и компилятор сообщает об ошибке. Для получения дополнительной информации см. [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
### <a name="correct-approach"></a>Правильный подход  
 Избегайте использования переменных с одинаковыми именами, но разными областями действия. При работе с другими сборками или проектами избегайте использования любых имен, определенных в их внешних компонентах, насколько это возможно. При наличии нескольких переменных с одним и тем же именем необходимо уточнить каждую ссылку на такую переменную. Для получения дополнительной информации см. [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>См. также

- [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Практическое руководство. Доступ к членам объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Практическое руководство. Определение типа, на который указывает объектная переменная](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
