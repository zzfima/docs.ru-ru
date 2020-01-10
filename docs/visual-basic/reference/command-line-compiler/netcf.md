---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 7f14ce07a2928f4dbffd3aa57f8cdd514b75694c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716712"
---
# <a name="-netcf"></a>-netcf

Задает компилятор, предназначенный для .NET Compact Framework.

## <a name="syntax"></a>Синтаксис

```console
-netcf
```

## <a name="remarks"></a>Заметки

Параметр `-netcf` заставляет компилятор Visual Basic нацелиться на .NET Compact Framework, а не на полный .NET Framework. Функции языка, существующие только в полной .NET Framework, отключены.

Параметр `-netcf` предназначен для использования с [-сдкпас](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Функции языка, отключенные `-netcf`, — это те же языковые возможности, которые отсутствуют в файлах, предназначенных для `-sdkpath`.

> [!NOTE]
> Параметр `-netcf` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки. Параметр `-netcf` задается при загрузке проекта Visual Basic устройства.

Параметр `-netcf` изменяет следующие языковые функции:

- Ключевое слово [End \<ключевое слово >](../../../visual-basic/language-reference/statements/end-keyword-statement.md) , которое завершает выполнение программы, отключено. Следующая программа компилируется и выполняется без `-netcf`, но при этом происходит сбой во время компиляции с `-netcf`.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- Позднее связывание во всех формах отключено. Ошибки времени компиляции генерируются при обнаружении сценариев с поздним связыванием. Следующая программа компилируется и выполняется без `-netcf`, но при этом происходит сбой во время компиляции с `-netcf`.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- Модификаторы [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)и [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) отключены. Синтаксис [инструкции DECLARE](../../../visual-basic/language-reference/statements/declare-statement.md) также изменяется на `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. В следующем коде показан результат `-netcf` компиляции.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- При использовании `-netcf` ключевые слова Visual Basic 6,0, которые были удалены из Visual Basic, выдает другую ошибку. Это влияет на сообщения об ошибках для следующих ключевых слов:

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a>Пример

Следующий код компилирует `Myfile.vb` с .NET Compact Framework, используя версии mscorlib. dll и Microsoft. VisualBasic. dll, найденные в .NET Compact Framework каталоге установки по умолчанию на диске C. Как правило, используется самая последняя версия .NET Compact Framework.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>См. также:

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
