---
title: 'Не удается выпустить сборку: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 012284aa42dfa29ad1a5e4ec4a4df5eaacbd4fb7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642277"
---
# <a name="unable-to-emit-assembly-error-message"></a>Не удается выпустить сборку: \<сообщение об ошибке >

Компилятор Visual Basic вызывает компоновщик сборок (*Al.exe*, которая также называется Alink) для создания сборки с манифестом и компоновщик сообщает об ошибке на этапе вывода создания сборки.

**Идентификатор ошибки:** BC30145

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Изучите приведенное сообщение об ошибке и обратитесь к разделу [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) для пояснения и рекомендации.

2. Попробуйте подписать сборку вручную, воспользовавшись [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) или [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).

3. Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.

### <a name="to-sign-the-assembly-manually"></a>Подпись сборки вручную

1. Используйте [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)) для создания файла пары открытого и закрытого ключей.

   Этот файл содержит *.snk* расширения.

2. Удалите из проекта ссылку COM, вызывающую ошибку.

3. Откройте [Командная строка разработчика для Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   В Windows 10, введите **Командная строка разработчика** в поле поиска на панели задач. Выберите **Командная строка разработчика для VS 2017** из списка результатов.

4. Перейдите в каталог в каталог, где вы хотите поместить программу-оболочку сборки.

5. Введите следующую команду:

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   Примером фактического команду, которую можно ввести является:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > Используйте двойные кавычки, если путь или файл содержит пробелы.

6. В Visual Studio добавьте ссылку на сборку .NET к файлу, который вы только что создали.

## <a name="see-also"></a>См. также

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [Практическое руководство. Создание пары открытого и закрытого ключей](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [Обращайтесь к нам](/visualstudio/ide/talk-to-us)
