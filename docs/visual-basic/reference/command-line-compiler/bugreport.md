---
title: /bugreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c36cdcaf8d2db0b08e262d6ba8ff2bb774fb233
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
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
|`file`|Обязательно. Имя файла, который будет содержать отчет об ошибке. Заключите имя файла в кавычки (» «), если имя содержит пробелы.|  
  
## <a name="remarks"></a>Примечания  
 Следующие сведения добавляется `file`:  
  
-   Копия всех файлов исходного кода при компиляции.  
  
-   Список параметров компилятора, используемые при компиляции.  
  
-   Сведения о версии о компилятора, среды CLR и операционной системы.  
  
-   Выходные данные компилятора (если есть).  
  
-   Описание проблемы, для которого будет предложено.  
  
-   Описание предполагаемого способа разрешения проблемы должны быть исправлены, для которого будет предложено.  
  
 Поскольку копия всех файлов исходного кода в `file`, может потребоваться воспроизвести предполагаемую ошибку в максимально короткой программе.  
  
> [!IMPORTANT]
>  `/bugreport` Параметр создает файл, который содержит конфиденциальные сведения. Это включает в себя текущее время, версия компилятора [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] версии, версия операционной системы, имя пользователя, аргументы командной строки, с помощью которых компилятор был запущен, весь код исходной и двоичной форме какой-либо связанной сборки. Этот параметр может осуществляться с помощью параметров командной строки в файле Web.config для серверных компиляция [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] приложения. Чтобы избежать этого, измените файл Machine.config следует запретить пользователям компиляцию на сервере.  
  
 Если этот параметр используется с `/errorreport:prompt`, `/errorreport:queue`, или `/errorreport:send`, и в приложении происходит внутренняя ошибка компилятора, сведения в `file` отправляется в корпорацию Майкрософт. Эти сведения помогут инженерам Майкрософт определить причину ошибки и помогут улучшить следующий выпуск [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. По умолчанию никакая информация отправляется в корпорацию Майкрософт. Тем не менее, при компиляции приложения с помощью `/errorreport:queue`, который включен по умолчанию, приложение собирает отчеты об ошибках. Затем при входе администратора система отчета об ошибках Отображает всплывающее окно, которое позволяет администратору переслать в корпорацию Майкрософт отчеты о любых ошибках, произошедших с момента входа в систему.  
  
> [!NOTE]
>  `/bugreport` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 В следующем примере компилируется `T2.vb` и помещает все сведения отчетность об ошибках в файле `Problem.txt`.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [trustLevel элемент для securityPolicy (схема параметров ASP.NET)](http://msdn.microsoft.com/library/729ab04c-03da-4ee5-86b1-be9d08a09369)
