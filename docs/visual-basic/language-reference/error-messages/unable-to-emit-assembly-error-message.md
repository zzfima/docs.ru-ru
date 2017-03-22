---
title: "Не удается выпустить сборку: &lt;сообщение об ошибке&gt; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
dev_langs:
- VB
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
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
ms.openlocfilehash: dac4b133882c043f9c84e936bad2e36f35fc4c33
ms.lasthandoff: 03/13/2017

---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>Не удается выпустить сборку: &lt;сообщение об ошибке&gt;
Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом, при этом компоновщик сообщает об ошибке на этапе предварительного выпуска процедуры создания сборки.  
  
 **Идентификатор ошибки:** BC30145  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Просмотрите сообщение об ошибке и обратитесь к разделу [Al.exe ошибки и предупреждения средства](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) для пояснения и рекомендации.  
  
2.  Попробуйте подписать сборку вручную, используя [компоновщик сборок (Al.exe)](https://msdn.microsoft.com/library/c405shex) или [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23).  
  
3.  Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
### <a name="to-sign-the-assembly-manually"></a>Подпись сборки вручную  
  
1.  Используйте [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23) для создания файла пары открытого и закрытого ключей.  
  
     Этот файл имеет расширение .SNK.  
  
2.  Удалите из проекта ссылку COM, вызывающую ошибку.  
  
3.  Из Windows **запустить** наведите указатель мыши на **программы**, пункты **Microsoft Visual Studio 2008**, пункты **средств Visual Studio**и нажмите кнопку **Командная строка Visual Studio 2008**.  
  
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
  
6.  В [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] добавьте в созданный файл ссылку на сборку .NET.  
  
## <a name="see-also"></a>См. также  
 [Al.exe (компоновщик сборок)](https://msdn.microsoft.com/library/c405shex)   
 [Ошибки и предупреждения программы Al.exe](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23)   
 [Практическое руководство. Создание пары открытого и закрытого ключей](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114)   
 [Обращайтесь к нам](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
