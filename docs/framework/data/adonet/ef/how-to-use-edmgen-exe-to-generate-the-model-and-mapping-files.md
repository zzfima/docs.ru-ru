---
title: Практическое руководство. Использование EdmGen.exe для создания файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: 8eb7e0c19d775e516765b0e88f61789a9136e6e1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467800"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Практическое руководство. Использование EdmGen.exe для создания файлов модели и сопоставления
В этом разделе показано, как с помощью средства «Генератор модели EDM» (EdmGen.exe) на основе базы данных School формируются следующие файлы:  
  
-   Концептуальная модель (CSDL-файл).  
  
-   Модель хранения (SSDL-файл).  
  
-   Сопоставление между концептуальной моделью и моделью хранения (MSL-файл).  
  
-   Код уровня объекта в Visual Basic или C#.  
  
-   Просмотр файлов.  
  
 Средство EdmGen.exe использует ключ /mode:FullGeneration для создания перечисленных выше файлов. Дополнительные сведения о командах EdmGen.exe см. в разделе [генератор модели EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).  
  
 Если вы используете EdmGen.exe для формирования файлов модели и сопоставления, необходимо по-прежнему настроить проект Visual Studio для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [как: вручную настроить проект Entity Framework](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Концептуальная модель, созданная с помощью средства EdmGen.exe, включает все объекты базы данных. При необходимости создания концептуальной модели, включающей только определенные объекты, следует использовать мастер моделей EDM. Дополнительные сведения см. в разделе [как: использовать мастер моделей EDM](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Создание модели School для проекта Visual Basic с помощью программы EdmGen.exe  
  
1.  Создайте базу данных School. Дополнительные сведения см. в разделе [Создание образца базы данных School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Создание модели School для проекта C# с помощью программы EdmGen.exe  
  
1.  Создайте базу данных School. Дополнительные сведения см. в разделе [Создание образца базы данных School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>См. также  
 [Моделирование и сопоставление](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [Практическое: вручную настроить проект Entity Framework](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [Практическое: заранее создать представления для повышения производительности запросов](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [Средства работы с моделью EDM ADO.NET](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
