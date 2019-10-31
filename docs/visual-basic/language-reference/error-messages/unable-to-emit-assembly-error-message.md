---
title: 'Не удается выпустить сборку: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 5776755a57fbc2b0086b1c9b6cfbb2f2b7eb03fa
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197272"
---
# <a name="unable-to-emit-assembly-error-message"></a>Не удалось выпустить сборку: \<сообщение об ошибке >

Компилятор Visual Basic вызывает компоновщик сборок (*Al. exe*, также известный как ALink) для создания сборки с манифестом, а компоновщик сообщает об ошибке на этапе эмиссии создания сборки.

**Идентификатор ошибки:** BC30145

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Изучите сообщение об ошибке в кавычках и ознакомьтесь с разделом [Al. exe](../../../framework/tools/al-exe-assembly-linker.md) для получения дополнительных пояснений и советов.

2. Попробуйте подписать сборку вручную, используя либо [Al. exe](../../../framework/tools/al-exe-assembly-linker.md) , либо [Sn. exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).

3. Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.

### <a name="to-sign-the-assembly-manually"></a>Подпись сборки вручную

1. Используйте [Sn. exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)) для создания файла пары открытого и закрытого ключей.

   Этот файл имеет расширение *SNK* .

2. Удалите из проекта ссылку COM, вызывающую ошибку.

3. Откройте [Командная строка разработчика для Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   В Windows 10 введите **командную строку разработчика** в поле поиска на панели задач. Затем выберите **Командная строка разработчика для VS 2017** в списке результатов.

4. Измените каталог на каталог, в который нужно поместить обертку сборки.

5. Введите следующую команду:

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   Пример реальной команды, которую можно ввести:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > Если путь или файл содержит пробелы, используйте двойные кавычки.

6. В Visual Studio добавьте ссылку на сборку .NET в только что созданный файл.

## <a name="see-also"></a>См. также

- [Al. exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [Практическое руководство. Создание пары открытого и закрытого ключей](../../../standard/assembly/create-public-private-key-pair.md)
- [Обращайтесь к нам](/visualstudio/ide/feedback-options)
