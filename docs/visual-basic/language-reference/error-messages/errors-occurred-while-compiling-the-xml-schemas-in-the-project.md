---
title: "При компиляции XML-схем в проекте возникли ошибки | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
dev_langs:
- VB
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
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
ms.openlocfilehash: cf04e85da98db53d1c78269169571936f708cd21
ms.lasthandoff: 03/13/2017

---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>При компиляции XML-схем в проекте возникли ошибки
При компиляции XML-схем в проекте возникли ошибки. В результате XML IntelliSense недоступна.  
  
 Имеется ошибка в схеме определения схемы XML (XSD), включенный в проект. Эта ошибка возникает при добавлении XSD-файл схемы (XSD), задать конфликтует с существующей схемой XSD для проекта.  
  
 **Идентификатор ошибки:** BC36810  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Дважды щелкните значок предупреждения в **список ошибок** окна. Visual Basic, вы перейдете расположение в XSD-файле, который является источником предупреждения. Исправление ошибки в схеме XSD.  
  
-   Убедитесь, что все необходимые файлы XSD-схемы (.xsd) включены в проект. Может потребоваться нажать **Показать все файлы** на **проекта** меню для просмотра вашего .xsd файлы в **обозревателе решений**. Щелкните правой кнопкой мыши XSD-файл и нажмите кнопку **включить в проект** для включения файла в проект.  
  
-   При использовании XML для мастера схем это ошибка может возникать, если схемы были получены более одного раза из одного источника. В этом случае можно удалить существующие файлы схемы XSD из проекта, добавить новый XML для шаблона элементов схемы и предоставьте XML для мастера схем всех источниками XML для проекта.  
  
-   Если ошибка не найдена в схеме XSD, компилятору XML может не иметь достаточно сведений, чтобы предоставить подробные сведения об ошибке. Возможно, удастся получить более подробные сведения об ошибке, если вы убедитесь, что пространства имен XML для XSD-файлы включены в проект, совпадают пространствами имен XML для XML-схемы в Visual Studio.  
  
## <a name="see-also"></a>См. также  
 [Окно списка ошибок](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window)   
 [XML IntelliSense в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
