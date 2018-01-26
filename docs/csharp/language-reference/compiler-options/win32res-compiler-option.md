---
title: "-win32res (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4c24da8bb745847612d882d00eff7f03dbc60475
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-win32res-c-compiler-options"></a>-win32res (параметры компилятора C#)
Параметр **-win32res** вставляет ресурс Win32 в выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Файл ресурсов, который требуется добавить в выходной файл.  
  
## <a name="remarks"></a>Примечания  
 Файл ресурсов Win32 можно создать с помощью [компилятора ресурсов](../../language-reference/compiler-options/resource-compiler-option.md). Компилятор ресурсов вызывается при компиляции программы Visual C++; RES-файл создается из RC-файла.  
  
 Ресурс Win32 может содержать сведения о версии или точечный рисунок (значок) для упрощения идентификации приложения в проводнике. Если параметр **-win32res** не задан, компилятор будет создавать сведения о версии на основе версии сборки.  
  
 Дополнительные сведения о ссылках на файлы ресурсов .NET Framework и их присоединении см. в разделах [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) и [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) соответственно.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Перейдите на страницу свойств **Приложение**.  
  
3.  Чтобы выбрать файл в поле со списком, нажмите кнопку **Файл ресурсов**.  
  
## <a name="example"></a>Пример  
 Скомпилируйте `in.cs` и присоедините файл ресурсов Win32 `rf.res`, чтобы создать `in.exe`:  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
