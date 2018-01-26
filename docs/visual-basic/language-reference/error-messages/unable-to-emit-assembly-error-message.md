---
title: "Не удается создать сборку: &lt;сообщение об ошибке&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords: BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b19b6439d85822c69adac0b3e0e04b2f31299836
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>Не удается создать сборку: &lt;сообщение об ошибке&gt;
Компилятор [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом, при этом компоновщик сообщает об ошибке на этапе предварительного выпуска процедуры создания сборки.  
  
 **Идентификатор ошибки:** BC30145  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Просмотрите сообщение об ошибке и обратитесь к разделу [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). содержатся дополнительные пояснения и рекомендации.  
  
2.  Попробуйте подписать сборку вручную, используя либо [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) или [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
3.  Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
### <a name="to-sign-the-assembly-manually"></a>Подпись сборки вручную  
  
1.  Используйте [Sn.exe (средство строгих имен)][Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)) для создания файла пары открытого и закрытого ключей.  
  
     Этот файл имеет расширение .SNK.  
  
2.  Удалите из проекта ссылку COM, вызывающую ошибку.  
  
3.  В окнах **запустить** последовательно выберите пункты **программы**, пункты **Microsoft Visual Studio 2008**, пункты **набора средств Visual Studio**, и Нажмите кнопку **Командная строка Visual Studio 2008**.  
  
4.  Перейдите в каталог, куда хотите поместить программу-оболочку сборки.  
  
5.  Введите следующий код.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     Ниже приведен пример кода, который вы можете ввести.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     Используйте двойные кавычки ("), если путь или файл содержат пробелы.  
  
6.  В [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] добавьте в созданный файл ссылку на сборку .NET.  
  
## <a name="see-also"></a>См. также  
 
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).  
 [Sn.exe (средство строгих имен)] [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md))  
 [Практическое руководство. Создание пары открытого и закрытого ключей](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [Обращайтесь к нам](/visualstudio/ide/talk-to-us)
