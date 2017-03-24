---
title: "/ bugreport | Документы Microsoft"
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
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
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
ms.openlocfilehash: 9c64ec49d7e6842edbc0fed7407a34132a8f5a88
ms.lasthandoff: 03/13/2017

---
# <a name="bugreport"></a>/bugreport
Создает файл, который можно использовать, если файл отчета об ошибке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`file`|Обязательный. Имя файла, который будет содержать отчет об ошибке. Заключите имя файла в кавычки (» «), если имя содержит пробелы.|  
  
## <a name="remarks"></a>Примечания  
 Добавляется следующее `file`:  
  
-   Копия всех файлов исходного кода при компиляции.  
  
-   Список использованных при компиляции параметров компилятора.  
  
-   Сведения о версии о компилятора, среды CLR и операционной системы.  
  
-   Выходные данные компилятора в, если таковые имеются.  
  
-   Описание проблемы, для которого будет предложено.  
  
-   Описание предполагаемого способа разрешения проблемы должна быть устранена, для которого будет предложено.  
  
 Поскольку копию всех файлов исходного кода в `file`, может потребоваться воспроизвести предполагаемую ошибку в максимально короткой программе.  
  
> [!IMPORTANT]
>  `/bugreport` Параметр создает файл, который содержит конфиденциальные сведения. Это включает в себя текущее время, версия компилятора [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] версии, версия операционной системы, имя пользователя, аргументы командной строки, с помощью которых компилятор был запущен, весь исходный код и двоичная форма какой-либо связанной сборки. Этот параметр может осуществляться с помощью параметров командной строки в файле Web.config для компиляции серверных [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] приложения. Чтобы избежать этого, измените файл Machine.config следует запретить пользователям компиляцию на сервере.  
  
 Если этот параметр используется с `/errorreport:prompt`, `/errorreport:queue`, или `/errorreport:send`, и в приложении происходит внутренняя ошибка компилятора, сведения в `file` отправляется корпорации Майкрософт. Эти сведения помогут инженерам Майкрософт определить причину ошибки и помогут улучшить следующий выпуск [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. По умолчанию никакая информация отправляется в корпорацию Майкрософт. Тем не менее, при компиляции приложения с помощью `/errorreport:queue`, который включен по умолчанию, приложение собирает отчеты об ошибках. Затем при входе в систему администратора системы отчетов об ошибках Отображает всплывающее окно, которое позволяет администратору переслать в корпорацию Майкрософт отчеты о любых ошибках, произошедших с момента входа в систему.  
  
> [!NOTE]
>  `/bugreport` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 В следующем примере компилируется `T2.vb` и помещает все сведения отчетность об ошибках в файле `Problem.txt`.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [/ ERRORREPORT](../../../visual-basic/reference/command-line-compiler/errorreport.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Элемент trustLevel для securityPolicy (схема параметров ASP.NET)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)
