---
title: "Устранение неполадок переменные в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9cddf7ced50c42514ebc9a613f49adee31edde0b
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-variables-in-visual-basic"></a>Устранение неполадок, связанных с переменными, в Visual Basic
На этой странице перечислены некоторые общие проблемы, которые могут возникнуть при работе с переменными в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="unable-to-access-members-of-an-object"></a>Не удается получить доступ к членам объекта  
 Если ваш код пытается получить доступ к свойству или методу объекта, могут возникнуть две следующие ошибки.  
  
-   Компилятор может создать сообщение об ошибке, если вы объявляете переменную объекта с определенным типом и затем ссылаетесь на член, не определенный этим типом.  
  
-   Время выполнения <xref:System.MemberAccessException>возникает, когда объект, присвоенный переменной объекта, не предоставляет элемент, код пытается получить доступ к.</xref:System.MemberAccessException> В случае переменная [тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md), можно также получить это исключение, если член не является `Public`. Это происходит потому, что позднее связывание разрешает доступ только к членам `Public` .  
  
 Когда [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) включает проверку типа `On`, переменной объекта доступны методы и свойства класса, в котором она объявлена. Это показано в следующем примере.  

 [!code-vb[VbVbalrVariables&#2;](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/troubleshooting-variables_1.vb)]  
  
 В этом примере `p` можно использовать только члены <xref:System.Object>, что сам класс, который не включает `Left` свойство.</xref:System.Object> С другой стороны `q` был объявлен с типом <xref:System.Windows.Forms.Label>, поэтому его можно использовать методы и свойства <xref:System.Windows.Forms.Label>класса в <xref:System.Windows.Forms>имен.</xref:System.Windows.Forms> </xref:System.Windows.Forms.Label> </xref:System.Windows.Forms.Label>  
  
### <a name="correct-approach"></a>Правильный подход  
 Чтобы иметь возможность доступа ко всем членам объекта определенного класса, объявите переменную объекта с типом этого класса, если это возможно. Если сделать это, нельзя, например, если вы не знаете тип во время компиляции объекта, необходимо задать `Option Strict` для `Off` и объявите переменную [тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md). В этом случае переменной могут быть присвоены объекты любого типа, а вы должны выполнить действия, чтобы убедиться, что текущий назначенный объект имеет допустимый тип. Можно использовать [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) для этого определения.  
  
## <a name="other-components-cannot-access-your-variable"></a>Другие компоненты не могут получить доступ к переменной  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]имена являются *без учета регистра*. Если два имени отличаются только регистром букв, компилятор интерпретирует их как одно и то же. Например, он считает, что `ABC` и `abc` являются одним и тем же объявленным элементом.  
  
 Однако среда CLR использует привязку *с учетом регистра* . Таким образом, при создании сборки или DLL и предоставлении к ней доступа другим сборкам, в именах регистр учитываться не будет. Например, если определен класс с элементом `ABC`и другие сборки используют класс с помощью среды CLR, они должны ссылаться на элемент как на `ABC`. Если впоследствии вы перекомпилируете класс и измените имя элемента на `abc`, другие сборки, использующие класс, больше не смогут обращаться к этому элементу. Таким образом, при выпуске обновленной версии сборки нельзя изменять регистр имен открытых элементов.  
  
 Дополнительные сведения см. в разделе [общеязыковая среда выполнения](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).  
  
### <a name="correct-approach"></a>Правильный подход  
 Чтобы другие компоненты получали доступ к переменным, рассматривайте их имена так, как если бы в них учитывался регистр. При тестировании класса или модуля убедитесь, что другие сборки выполняют привязку к нужным переменным. После публикации компонента не изменяйте существующие имена переменных и их регистр.  
  
## <a name="wrong-variable-being-used"></a>Используется неправильная переменная  
 При наличии более одной переменной с тем же именем [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор пытается разрешить каждую ссылку на это имя. Если переменные имеют различные области действия, компилятор разрешает ссылку на объявление с самой узкой областью. Если они имеют одну и ту же область действия, разрешение не выполняется и компилятор сообщает об ошибке. Дополнительные сведения см. в разделе [ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
### <a name="correct-approach"></a>Правильный подход  
 Избегайте использования переменных с одинаковыми именами, но разными областями действия. При работе с другими сборками или проектами избегайте использования любых имен, определенных в их внешних компонентах, насколько это возможно. При наличии нескольких переменных с одним и тем же именем необходимо уточнить каждую ссылку на такую переменную. Дополнительные сведения см. в разделе [ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>См. также  
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Объявление переменных объектов](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Практическое руководство: доступ к членам объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Практическое руководство: определение типа, который указывает объектная переменная](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
