---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005504"
---
# <a name="-main"></a>-main
Задает класс или модуль, содержащий процедуру `Sub Main`.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a>Аргументы  
 `location`  
 Обязательный. Имя класса или модуля, который содержит процедуру `Sub Main`, вызываемую при запуске программы. Это может быть в формате " **основной: модуль** " или " **основной: пространство имен. модуль**".  
  
## <a name="remarks"></a>Примечания  
 Используйте этот параметр при создании исполняемого файла или исполняемой программы Windows. Если параметр **-Main** пропущен, компилятор выполняет поиск допустимого общего `Sub Main` во всех открытых классах и модулях.  
  
 Описание различных форм процедуры `Main` см. [в разделе Главная процедура в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) .  
  
 Если `location` является классом, который наследует от <xref:System.Windows.Forms.Form>, компилятор предоставляет процедуру `Main` по умолчанию, которая запускает приложение, если у класса нет процедуры `Main`. Это позволяет компилировать код в командной строке, созданной в среде разработки.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Настройка-Main в интегрированной среде разработки Visual Studio  
  
1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2. Перейдите на вкладку **Приложение** .  
  
3. Убедитесь, что флажок **Включить платформу приложений** не установлен.  
  
4. Измените значение в поле **автоматически запускаемый объект** .  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и `T3.vb`, указывая, что процедура `Sub Main` будет найдена в классе `Test2`.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Главная процедура в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
