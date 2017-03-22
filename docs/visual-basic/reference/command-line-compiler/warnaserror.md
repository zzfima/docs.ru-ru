---
title: "/ warnaserror (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
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
ms.openlocfilehash: 28f232b1ad8200455550f2f4c1204818c8b143ab
ms.lasthandoff: 03/13/2017

---
# <a name="warnaserror-visual-basic"></a>/warnaserror (Visual Basic)
Указывает компилятору обрабатывать первое предупреждение как ошибку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|+ &#124; -|Необязательный. По умолчанию `/warnaserror-` — фактически; предупреждения не запретить компилятору создавать выходной файл. `/warnaserror` Вариант, который одинаков как `/warnaserror+`, предупреждения обрабатываются как ошибки.|  
|`numberList`|Необязательный. Разделенный запятыми список идентификаторов предупреждений числа, к которому `/warnaserror` применяется параметр. Если идентификатор предупреждения не указан, `/warnaserror` параметр применяется ко всем предупреждениям.|  
  
## <a name="remarks"></a>Примечания  
 `/warnaserror` Обрабатывает все предупреждения как ошибки. Все сообщения, которые обычно рассматриваются как предупреждения, выводятся как ошибки. Компилятор сообщает следующие вхождения того же предупреждения как предупреждения.  
  
 По умолчанию `/warnaserror-` , в результате чего предупреждения только в информационных целях. `/warnaserror` Вариант, который одинаков как `/warnaserror+`, предупреждения обрабатываются как ошибки.  
  
 Если требуется только несколько определенных предупреждений, которые обрабатываются как ошибки, можно указать разделенный запятыми список номеров предупреждений, которые следует обрабатывать как ошибки.  
  
> [!NOTE]
>  `/warnaserror` Не управляет способом отображения предупреждений. Используйте [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) параметр, чтобы отключить предупреждения.  
  
|Установка параметра/warnaserror для обработки всех предупреждений как ошибок в Интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Откройте вкладку **Компиляция**.<br />3.  Убедитесь, что **отключить все предупреждения** флажок снят.<br />4.  Проверьте **обрабатывать все предупреждения как ошибки** флажок.|  
  
|Установка параметра/warnaserror для обработки выбранных предупреждений как ошибок в Интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**.<br />2.  Откройте вкладку **Компиляция**.<br />3.  Убедитесь, что **отключить все предупреждения** флажок снят.<br />4.  Убедитесь, что **обрабатывать все предупреждения как ошибки** флажок снят.<br />5.  Выберите **ошибка** из **уведомления** столбец рядом с предупреждением, которое должно обрабатываться как ошибки.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` , а компилятор отображает ошибку для первого вхождения каждого предупреждения.  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и обрабатывает только предупреждения для неиспользуемых локальных переменных (42024) как ошибка.  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Настройка предупреждений в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)
