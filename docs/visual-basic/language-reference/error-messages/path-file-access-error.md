---
title: "Ошибка доступа к файлу путь | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
dev_langs:
- VB
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: ac730bac76540331206daebe600445ca54cc15a9
ms.lasthandoff: 03/13/2017

---
# <a name="pathfile-access-error"></a>Ошибка доступа к пути/файлу
Во время операции доступа к файлам или доступа к диску операционной системы не удается установить связь между путь и имя файла.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что спецификация файла правильно отформатирован. Имя файла может содержать полный (абсолютный) или относительный путь. Полный путь начинается с имени диска (если путь находится на другом диске) и содержит явный путь от корня к файлу. Любой путь, который не является полным задается относительно текущего диска и каталога.  
  
2.  Убедитесь, что вы не была предпринята попытка сохранить файл, который заменит существующий файл только для чтения. Если это так, измените атрибут только для чтения целевого файла или сохраните файл с другим именем файла.  
  
3.  Убедитесь, что не была предпринята попытка открыть файл только для чтения в режиме`Output`или `Append` режиме. Если это так, откройте файл в `Input` режиме или измените атрибут "только для чтения" файла.  
  
4.  Убедитесь, что не была предпринята попытка изменить [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проекта в пределах базы данных или документа.  
  
## <a name="see-also"></a>См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)
