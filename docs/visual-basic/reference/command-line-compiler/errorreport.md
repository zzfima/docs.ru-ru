---
title: "/ ERRORREPORT | Документы Microsoft"
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
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ebe5646256926f68a1a900b91c25a1768505785
ms.lasthandoff: 03/13/2017

---
# <a name="errorreport"></a>/errorreport
Указывает, как компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должен сообщать о внутренних ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр предоставляет удобный способ отчета [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Внутренняя ошибка компилятора (ICE) для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] корпорации Microsoft. По умолчанию компилятор отправляет никакие сведения в корпорацию Майкрософт. Однако при возникновении внутренней ошибки компилятора, этот параметр позволяет отчет об ошибке в корпорацию Майкрософт. Эти сведения помогут инженерам Майкрософт определить причину и помогут улучшить следующий выпуск [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Возможность отправки отчетов зависит от разрешений политики компьютера и пользователя.  
  
 В следующей таблице перечислены эффект `/errorreport` параметр.  
  
|Параметр|Поведение|  
|---|---|  
|`prompt`|При возникновении внутренней ошибки компилятора, диалоговое окно появится, можно просмотреть точные данные, собранные компилятором. Можно определить, если важную информацию в отчет об ошибке и принять решение о том, следует ли отправлять их в корпорацию Майкрософт. Если вы решили отправить его разрешена параметрами политики компьютера и пользователя, компилятор отправляет данные в корпорацию Майкрософт.|  
|`queue`|Очереди отчета об ошибках. При входе в систему с правами администратора может обо всех сбоях с момента последнего входа (вы не предлагается отправлять отчеты об ошибках, более одного раза в три дня). Это поведение по умолчанию при `/errorreport` параметр не указан.|  
|`send`|Если происходит внутренняя ошибка компилятора, и разрешена параметрами политики компьютера и пользователя, компилятор отправляет данные в корпорацию Майкрософт.<br /><br /> Параметр `/errorReport:send` пытается автоматически отправлять информацию об ошибках в корпорацию Майкрософт. Этот параметр зависит от реестра. Дополнительные сведения о настройке соответствующих значений в реестре в разделе [как включить автоматическое создание отчетов об ошибках в средствах командной строки Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).|  
|`none`|При возникновении внутренней ошибки компилятора, его не быть собираются и отправляются в корпорацию Майкрософт.|  
  
 Компилятор отправляет данные, включающие стека во время ошибки, которая обычно включает некоторые исходный код. Если `/errorreport` используется с [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) параметр, а затем отправляется весь исходный файл.  
  
 Этот параметр лучше всего использовать с [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) вариант, поскольку он позволяет инженерам корпорации Майкрософт более легко воспроизвести ошибку.  
  
> [!NOTE]
>  `/errorreport` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код попытается скомпилировать `T2.vb`, и если компилятор обнаруживает Внутренняя ошибка компилятора, будет предложено отправить отчет об ошибках в корпорацию Майкрософт.  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
