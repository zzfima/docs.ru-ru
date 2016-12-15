---
title: "/bugreport | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/bugreport - параметр компилятора [Visual Basic]"
  - "bugreport - параметр компилятора [Visual Basic]"
  - "-bugreport - параметр компилятора [Visual Basic]"
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /bugreport
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Создает файл, который можно использовать для отправки отчета об ошибках.  
  
## Синтаксис  
  
```  
/bugreport:file  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`file`|Обязательный.  Имя файла, содержащего отчет об ошибке.  Заключите имя файла в кавычки \(" "\), если оно содержит пробел.|  
  
## Заметки  
 К `file` добавляются следующие сведения:  
  
-   Копия всех исходных файлов, участвующих в компиляции.  
  
-   Список использованных при компиляции параметров компилятора.  
  
-   Сведения о версии компилятора, среде CLR и операционной системе.  
  
-   Скомпилированный код \(при его наличии\).  
  
-   Описание проблемы, которое запрашивается у пользователя.  
  
-   Описание предполагаемого способа разрешения проблемы, которое запрашивается у пользователя.  
  
 Поскольку все исходные файлы кода копируются в файл `file`, можно попытаться воспроизвести предполагаемую ошибку в максимально короткой программе.  
  
> [!IMPORTANT]
>  Параметр `/bugreport` создает файл, содержащий потенциально важные данные.  К ним относится текущее время, версия компилятора, версия [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], версия операционной системы, имя пользователя, аргументы командной строки, с которой компилятор был запущен, весь исходный код и двоичная форма всех используемых сборок.  Данный параметр доступен с помощью параметров командной строки файла Web.config при серверной компиляции приложения [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].  Чтобы избежать этого, следует запретить пользователям компиляцию на сервере, отредактировав файл Machine.config.  
  
 Если этот параметр используется с параметром `/errorreport:prompt`, `/errorreport:queue` или `/errorreport:send`, и в приложении возникает внутренняя ошибка компилятора, то сведения в `file` отправляются в корпорацию Майкрософт.  Эти сведения помогут инженерам Майкрософт определить причину ошибки и помогут улучшить следующий выпуск [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  По умолчанию данные не отправляются в корпорацию Майкрософт.  Тем не менее, при компиляции приложения с помощью параметра `/errorreport:queue`, который включен по умолчанию, приложение собирает отчеты об ошибках.  Затем, когда администратор входит в систему, система отчета об ошибках отображает всплывающее окно, которое позволяет администратору переслать в корпорацию Майкрософт отчеты о любых ошибках, произошедших с момента входа в систему.  
  
> [!NOTE]
>  Параметр `/bugreport` недоступен из среды разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## Пример  
 В следующем примере компилируется `T2.vb` и вся информация об ошибках помещается в файл `Problem.txt`.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/debug](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [\/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Элемент trustLevel для элемента securityPolicy \(схема параметров ASP.NET\)](http://msdn.microsoft.com/ru-ru/729ab04c-03da-4ee5-86b1-be9d08a09369)