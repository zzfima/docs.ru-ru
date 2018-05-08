---
title: Локализация действий
ms.date: 03/30/2017
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
ms.openlocfilehash: 23a6d5c2ed202f030397eb70382896468a68a724
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="activity-localization"></a>Локализация действий
Если приложения и компоненты рабочего процесса могут подлежать локализации для других языков и адаптации к особенностям других регионов, то в них следует использовать строки ресурсов, чтобы локализацию можно было провести без перекомпилирования.  
  
## <a name="activity-localization"></a>Локализация действий  
 Как и при работе со всеми локализуемыми приложениями (выпускаемыми в различных версиях для различных языков и различных региональных стандартов), все отображаемые пользователю строки должны храниться в файле ресурсов, а не находиться в коде. Строки может осуществляться через <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`. При разработке компонента, распространяемого на различных языках, строки ресурсов также следует применять для сообщений проверки допустимости действий, определяемых пользователем данных отслеживания, сообщений трассировки и сообщений об ошибках.  
  
 В следующем примере демонстрируется применение файла ресурсов.  
  
#### <a name="using-resource-files-for-localized-strings"></a>Использование файлов ресурсов для локализованных строк  
  
1.  В [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], щелкните правой кнопкой мыши проект в **обозревателе решений** и выберите **добавить...** , **Новый элемент...** .  
  
2.  Выберите **файл ресурсов** и назовите файл ErrorResources.resx. Нажмите кнопку **Добавить**.  
  
3.  Откройте файл ресурсов. Добавить новую запись с **имя** из ErrorString и **значение** из «действие недопустимо.»  
  
4.  Добавьте к классу следующие инструкции `using`.  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
    ```  
  
5.  Создайте в проекте диспетчер ресурсов.  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
    ```  
  
6.  При необходимости строку можно получать из диспетчера ресурсов.  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
    ```  
  
 В следующем образце кода показано использование локализованных строк в методе <xref:System.Activities.Activity.CacheMetadata%2A>.  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```
