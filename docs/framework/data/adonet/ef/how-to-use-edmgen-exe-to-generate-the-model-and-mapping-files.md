---
title: Практическое руководство. Использование EdmGen.exe для создания файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: c74f9344891d43f21034a48ac51723fa7441744d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040308"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Практическое руководство. Использование EdmGen.exe для создания файлов модели и сопоставления
В этом разделе показано, как с помощью средства «Генератор модели EDM» (EdmGen.exe) на основе базы данных School формируются следующие файлы:  
  
- Концептуальная модель (CSDL-файл).  
  
- Модель хранения (SSDL-файл).  
  
- Сопоставление между концептуальной моделью и моделью хранения (MSL-файл).  
  
- Код уровня объекта в Visual Basic или C#.  
  
- Просмотр файлов.  
  
 Средство EdmGen.exe использует ключ /mode:FullGeneration для создания перечисленных выше файлов. Дополнительные сведения о командах EdmGen. exe см. в разделе [генератор EDM (EdmGen. exe)](edm-generator-edmgen-exe.md).  
  
 Если для создания файлов модели и сопоставления используется Программа EdmGen. exe, по-прежнему необходимо настроить проект Visual Studio для использования Entity Framework. Дополнительные сведения см. [в разделе как вручную настроить проект Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
> [!NOTE]
> Концептуальная модель, созданная с помощью средства EdmGen.exe, включает все объекты базы данных. При необходимости создания концептуальной модели, включающей только определенные объекты, следует использовать мастер моделей EDM. Дополнительные сведения см. в разделе [инструкции. Использование мастера EDM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Создание модели School для проекта Visual Basic с помощью программы EdmGen.exe  
  
1. Создайте базу данных School. Дополнительные сведения см. [в разделе Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Создание модели School для проекта C# с помощью программы EdmGen.exe  
  
1. Создайте базу данных School. Дополнительные сведения см. [в разделе Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>См. также

- [Моделирование и сопоставление](modeling-and-mapping.md)
- [Как вручную настроить проект Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Как предварительно создавать представления для повышения производительности запросов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Средства EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
