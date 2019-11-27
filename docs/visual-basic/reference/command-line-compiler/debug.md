---
title: /debug
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 3beb9ad3829c2f55120a9136e6e54185551bd20b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344777"
---
# <a name="-debug-visual-basic"></a>-Debug (Visual Basic)

Приводит к тому, что компилятор создает отладочную информацию и помещает ее в выходные файлы.

## <a name="syntax"></a>Синтаксис

```console
-debug[+ | -]
```

или

```console
-debug:[full | pdbonly]
```

## <a name="arguments"></a>Аргументы

|Термин|Определение|
|---|---|
|`+` &#124; `-`|Необязательный элемент. Указание `+` или `/debug` приводит к тому, что компилятор создает отладочную информацию и помещает ее в PDB-файл. Указание `-` имеет тот же результат, что и не указывает `/debug`.|
|`full` &#124; `pdbonly`|Необязательный элемент. Определяет тип отладочной информации, создаваемой компилятором. Если не указать `/debug:pdbonly`, по умолчанию будет `full`, что позволит подключить отладчик к выполняющейся программе. Аргумент `pdbonly` позволяет выполнять отладку исходного кода при запуске программы в отладчике, но отображает код на языке ассемблера, только если выполняющаяся программа подключена к отладчику.|

## <a name="remarks"></a>Примечания

Используйте этот параметр для создания отладочных сборок. Если не указать `/debug`, `/debug+`или `/debug:full`, вы не сможете выполнить отладку выходного файла программы.

По умолчанию отладочная информация не создается (`/debug-`). Чтобы выдать отладочную информацию, укажите `/debug` или `/debug+`.

Сведения о настройке производительности отладки для приложения см. в разделе [Упрощение отладки образов](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).

|Установка-Debug в интегрированной среде разработки Visual Studio|
|---|
|1. выбрав проект в **Обозреватель решений**, в меню **проект** выберите пункт **Свойства**. <br />2. Перейдите на вкладку **Компиляция** .<br />3. Нажмите кнопку **Дополнительные параметры компиляции**.<br />4. Измените значение в поле **создать сведения об отладке** .|

## <a name="example"></a>Пример

В следующем примере отладочная информация помещается в выходной файл `App.exe`.

```console
vbc -debug -out:app.exe test.vb
```

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
