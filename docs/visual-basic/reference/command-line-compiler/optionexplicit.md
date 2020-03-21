---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266733"
---
# <a name="-optionexplicit"></a>-optionexplicit
Вызывает сообщение об ошибках компилятора, если переменные не объявляются до их использования.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный параметр. Указать, `-optionexplicit+` чтобы требовать явного объявления переменных. Опция `-optionexplicit+` по умолчанию и `-optionexplicit`такая же, как . Опция `-optionexplicit-` позволяет неявно декларирование переменных.  
  
## <a name="remarks"></a>Remarks  
 Если файл исходного кода содержит [заявление Option Explicit,](../../../visual-basic/language-reference/statements/option-explicit-statement.md)заявление переопределяет настройки `-optionexplicit` компилятора командной строки.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Установить -опцию в Visual Studio IDE  
  
1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите **Свойства**.
  
2. Откройте вкладку **Компиляция**.  
  
3. Измените значение в поле **Option Explicit.**  
  
## <a name="example"></a>Пример  
 Следующий код компилируется при `-optionexplicit-` использовании.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>См. также раздел

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
