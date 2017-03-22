---
title: "/ main | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dded7621845141896f353d69ab757010c825b975
ms.lasthandoff: 03/13/2017

---
# <a name="main"></a>/main
Указывает класс или модуль, содержащий `Sub Main` процедуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/main:location  
```  
  
## <a name="arguments"></a>Аргументы  
 `location`  
 Обязательный. Полное имя пространства имен для класса или модуля, содержащего `Sub Main` процедуры, который должен вызываться при запуске программы. Это может быть в форме **/main:module** или **/main:namespace.module**.  
  
## <a name="remarks"></a>Примечания  
 Используйте этот параметр при создании исполняемого файла или программы для Windows. Если **/main** параметр указан, компилятор выполняет поиск допустимый общий `Sub Main` во всех открытых классов и модулей.  
  
 В разделе [процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) обсуждение различных видов `Main` процедуры.  
  
 Когда `location` — это класс, который наследует от <xref:System.Windows.Forms.Form>, компилятор предоставляет значение по умолчанию `Main` процедуру, которая запускает приложение, если класс не имеет `Main` процедуры.</xref:System.Windows.Forms.Form> Это позволяет скомпилировать код из командной строки, который был создан в среде разработки.  
  
 [!code-vb[VbVbalrCompiler №&16;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a>Чтобы установить параметр/Main в Visual Studio интегрированная среда разработки  
  
1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**.  
  
     Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Перейдите на вкладку **Приложение** .  
  
3.  Убедитесь, что **Включить исполняющую среду** не установлен флажок.  
  
4.  Измените значение в **автоматически запускаемый объект** поле.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и `T3.vb`, указав, `Sub Main` процедуры будут находиться в `Test2` класса.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [NIB: версия Visual Basic Hello World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)   
 [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
