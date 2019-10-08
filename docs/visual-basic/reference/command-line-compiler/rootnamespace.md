---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: 4df4e74fc13c922f51f5b74c3c152bdea28b4431
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005213"
---
# <a name="-rootnamespace"></a>-rootnamespace
Задает пространство имен для всех объявлений типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`namespace`|Имя пространства имен, в котором должны быть заключены все объявления типов для текущего проекта.|  
  
## <a name="remarks"></a>Примечания  
 Если вы используете исполняемый файл Visual Studio (devenv. exe) для компиляции проекта, созданного в интегрированной среде разработки Visual Studio, используйте `-rootnamespace`, чтобы указать значение свойства <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>. Дополнительные сведения см. в разделе [devenv параметры командной строки](/visualstudio/ide/reference/devenv-command-line-switches) .  
  
 Используйте дизассемблер MSIL среды CLR (`Ildasm.exe`) для просмотра имен пространств имен в выходном файле.  
  
|Установка параметра-RootNamespace в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в поле **корневое пространство имен** .|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и заключает все объявления типов в пространство имен `mynamespace`.  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Ildasm.exe (дизассемблер IL)](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
