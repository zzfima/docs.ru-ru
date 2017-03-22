---
title: "Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
dev_langs:
- VB
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
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
ms.openlocfilehash: 35a912bbcab78178ce636afa550c244823da512c
ms.lasthandoff: 03/13/2017

---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt;
Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом. Компоновщик сообщил об ошибке на этапе предварительного выпуска процедуры создания сборки.  
  
 Такая ситуация может возникнуть при наличии проблем с указанным файлом ключа или контейнером ключей. Чтобы использовать для сборки полную подпись, необходимо предоставить допустимый файл ключа с информацией об открытом и закрытом ключах. Чтобы отложить подпись сборки, необходимо выбрать **отложенную подпись только** флажок и предоставить допустимый файл ключей, содержащий сведения об открытом ключе. При использовании отложенной подписи для сборки наличие закрытого ключа не требуется. Дополнительные сведения см. в разделе [как: подписать сборку (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).  
  
 **Идентификатор ошибки:** BC30140  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Просмотрите сообщение об ошибке и обратитесь к разделу [Al.exe ошибки и предупреждения средства](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) по ошибке AL1019 дополнительные пояснения и рекомендации  
  
2.  Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Подписывание сборки (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)   
 [Страница "Подписывание" в конструкторе проектов](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer)   
 [Al.exe (компоновщик сборок)](https://msdn.microsoft.com/library/c405shex)   
 [Ошибки и предупреждения программы Al.exe](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Обращайтесь к нам](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
