---
title: "-debug (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /debug
helpviewer_keywords:
- debug compiler option [C#]
- -debug compiler option [C#]
- /debug compiler option [C#]
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4705fc6fc3e3fa41f46b8617aa23ab507afa0cd1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="debug-c-compiler-options"></a>/debug (параметры компилятора C#)
При заданном параметре **/debug** компилятор создает отладочную информацию и помещает ее в выходном файле или файлах.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/debug[+ | -]  
/debug:{full | pdbonly}  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 При задании `+` или только **/debug** компилятор создает отладочную информацию и помещает ее в базу данных программы (файл с расширением PDB). Если задан параметр `-`, который работает при отсутствии параметра **/debug**, отладочные данные не создаются.  
  
 `full` &#124; `pdbonly`  
 Определяет тип отладочной информации, создаваемой компилятором. Аргумент full, действующий при отсутствии параметра **/debug:pdbonly**, позволяет присоединить отладчик к выполняющейся программе. Задание параметра pdbonly позволяет выполнять отладку исходного кода при запуске программы в отладчике, но при этом ассемблер отображается только при подключении выполняющейся программы к отладчику.  
  
## <a name="remarks"></a>Примечания  
 Используйте этот параметр для создания отладочных сборок. Если не задать параметр**/debug**, **/debug+** или **/debug:full**, то отладка выходного файла программы будет невозможна.  
  
 При использовании параметра **/debug:full** необходимо учитывать некоторое влияние на скорость и размер оптимизированного кода JIT и незначительное влияние на качество кода с **/debug:full**. Для создания кода выпуска рекомендуется использовать параметр **/debug:pdbonly** либо не использовать PDB.  
  
> [!NOTE]
>  Отличие **/debug:pdbonly** от **/debug:full** заключается в том, что компилятор с параметром **/debug:full** создает <xref:System.Diagnostics.DebuggableAttribute>, сообщающий JIT-компилятору о доступности отладочных сведений. Поэтому если при использовании параметра **/debug:full** код содержит <xref:System.Diagnostics.DebuggableAttribute> со значением false, будет выведено сообщение об ошибке.  
  
 Дополнительные сведения о настройке производительности отладки для приложения см. в разделе [Упрощение отладки образов](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
 Чтобы изменить расположение PDB-файла, см. раздел [/pdb (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Щелкните страницу свойств **Сборка**.  
  
3.  Нажмите кнопку **Дополнительно** .  
  
4.  Измените свойство **Сведения для отладки**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>.  
  
## <a name="example"></a>Пример  
 Разместите отладочную информацию в выходном файле `app.pdb`.  
  
```console  
csc /debug /pdb:app.pdb test.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
