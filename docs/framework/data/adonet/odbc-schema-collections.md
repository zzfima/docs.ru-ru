---
title: Коллекции схемы ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43479984"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="954b2-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="954b2-102">ODBC Schema Collections</span></span>
<span data-ttu-id="954b2-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="954b2-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="954b2-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="954b2-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="954b2-105">Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="954b2-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="954b2-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="954b2-106">Tables</span></span>  
  
-   <span data-ttu-id="954b2-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="954b2-107">Indexes</span></span>  
  
-   <span data-ttu-id="954b2-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="954b2-108">Columns</span></span>  
  
-   <span data-ttu-id="954b2-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="954b2-109">Procedures</span></span>  
  
-   <span data-ttu-id="954b2-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="954b2-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="954b2-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="954b2-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="954b2-112">Представления</span><span class="sxs-lookup"><span data-stu-id="954b2-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="954b2-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="954b2-113">Tables and Views</span></span>  
  
|<span data-ttu-id="954b2-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-114">ColumnName</span></span>|<span data-ttu-id="954b2-115">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="954b2-116">TABLE_CAT</span></span>|<span data-ttu-id="954b2-117">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-117">String</span></span>|  
|<span data-ttu-id="954b2-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="954b2-118">TABLE_SCHEM</span></span>|<span data-ttu-id="954b2-119">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-119">String</span></span>|  
|<span data-ttu-id="954b2-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-120">TABLE_NAME</span></span>|<span data-ttu-id="954b2-121">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-121">String</span></span>|  
|<span data-ttu-id="954b2-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-122">TABLE_TYPE</span></span>|<span data-ttu-id="954b2-123">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-123">String</span></span>|  
|<span data-ttu-id="954b2-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-124">REMARKS</span></span>|<span data-ttu-id="954b2-125">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="954b2-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="954b2-126">Indexes</span></span>  
  
|<span data-ttu-id="954b2-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-127">ColumnName</span></span>|<span data-ttu-id="954b2-128">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="954b2-129">TABLE_CAT</span></span>|<span data-ttu-id="954b2-130">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-130">String</span></span>|  
|<span data-ttu-id="954b2-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="954b2-131">TABLE_SCHEM</span></span>|<span data-ttu-id="954b2-132">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-132">String</span></span>|  
|<span data-ttu-id="954b2-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-133">TABLE_NAME</span></span>|<span data-ttu-id="954b2-134">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-134">String</span></span>|  
|<span data-ttu-id="954b2-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="954b2-135">NON_UNIQUE</span></span>|<span data-ttu-id="954b2-136">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-136">Int16</span></span>|  
|<span data-ttu-id="954b2-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="954b2-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="954b2-138">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-138">String</span></span>|  
|<span data-ttu-id="954b2-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-139">INDEX_NAME</span></span>|<span data-ttu-id="954b2-140">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-140">String</span></span>|  
|<span data-ttu-id="954b2-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-141">TYPE</span></span>|<span data-ttu-id="954b2-142">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-142">Int16</span></span>|  
|<span data-ttu-id="954b2-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="954b2-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="954b2-144">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-144">Int16</span></span>|  
|<span data-ttu-id="954b2-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-145">COLUMN_NAME</span></span>|<span data-ttu-id="954b2-146">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-146">String</span></span>|  
|<span data-ttu-id="954b2-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="954b2-147">ASC_OR_DESC</span></span>|<span data-ttu-id="954b2-148">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-148">String</span></span>|  
|<span data-ttu-id="954b2-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="954b2-149">CARDINATLITY</span></span>|<span data-ttu-id="954b2-150">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-150">Int32</span></span>|  
|<span data-ttu-id="954b2-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="954b2-151">PAGES</span></span>|<span data-ttu-id="954b2-152">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-152">Int32</span></span>|  
|<span data-ttu-id="954b2-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="954b2-153">FILTER_CONDITION</span></span>|<span data-ttu-id="954b2-154">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-154">String</span></span>|  
|<span data-ttu-id="954b2-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="954b2-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="954b2-156">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-156">String</span></span>|  
|<span data-ttu-id="954b2-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="954b2-158">Byte</span><span class="sxs-lookup"><span data-stu-id="954b2-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="954b2-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="954b2-159">Columns</span></span>  
  
|<span data-ttu-id="954b2-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-160">ColumnName</span></span>|<span data-ttu-id="954b2-161">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="954b2-162">TABLE_CAT</span></span>|<span data-ttu-id="954b2-163">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-163">String</span></span>|  
|<span data-ttu-id="954b2-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="954b2-164">TABLE_SCHEM</span></span>|<span data-ttu-id="954b2-165">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-165">String</span></span>|  
|<span data-ttu-id="954b2-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-166">TABLE_NAME</span></span>|<span data-ttu-id="954b2-167">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-167">String</span></span>|  
|<span data-ttu-id="954b2-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-168">COLUMN_NAME</span></span>|<span data-ttu-id="954b2-169">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-169">String</span></span>|  
|<span data-ttu-id="954b2-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-170">DATA_TYPE</span></span>|<span data-ttu-id="954b2-171">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-171">Int16</span></span>|  
|<span data-ttu-id="954b2-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-172">TYPE_NAME</span></span>|<span data-ttu-id="954b2-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-173">String</span></span>|  
|<span data-ttu-id="954b2-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="954b2-174">COLUMN_SIZE</span></span>|<span data-ttu-id="954b2-175">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-175">Int32</span></span>|  
|<span data-ttu-id="954b2-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="954b2-177">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-177">Int32</span></span>|  
|<span data-ttu-id="954b2-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="954b2-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="954b2-179">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-179">Int16</span></span>|  
|<span data-ttu-id="954b2-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="954b2-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="954b2-181">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-181">Int16</span></span>|  
|<span data-ttu-id="954b2-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-182">NULLABLE</span></span>|<span data-ttu-id="954b2-183">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-183">Int16</span></span>|  
|<span data-ttu-id="954b2-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-184">REMARKS</span></span>|<span data-ttu-id="954b2-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-185">String</span></span>|  
|<span data-ttu-id="954b2-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="954b2-186">COLUMN_DEF</span></span>|<span data-ttu-id="954b2-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-187">String</span></span>|  
|<span data-ttu-id="954b2-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="954b2-189">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-189">Int16</span></span>|  
|<span data-ttu-id="954b2-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="954b2-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="954b2-191">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-191">Int16</span></span>|  
|<span data-ttu-id="954b2-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="954b2-193">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-193">Int32</span></span>|  
|<span data-ttu-id="954b2-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="954b2-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="954b2-195">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-195">Int32</span></span>|  
|<span data-ttu-id="954b2-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-196">IS_NULLABLE</span></span>|<span data-ttu-id="954b2-197">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-197">String</span></span>|  
|<span data-ttu-id="954b2-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="954b2-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="954b2-199">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-199">String</span></span>|  
|<span data-ttu-id="954b2-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="954b2-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="954b2-201">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-201">String</span></span>|  
|<span data-ttu-id="954b2-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="954b2-203">Byte</span><span class="sxs-lookup"><span data-stu-id="954b2-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="954b2-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="954b2-204">Procedures</span></span>  
  
|<span data-ttu-id="954b2-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-205">ColumnName</span></span>|<span data-ttu-id="954b2-206">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="954b2-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="954b2-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-208">String</span></span>|  
|<span data-ttu-id="954b2-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="954b2-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="954b2-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-210">String</span></span>|  
|<span data-ttu-id="954b2-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="954b2-212">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-212">String</span></span>|  
|<span data-ttu-id="954b2-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="954b2-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="954b2-214">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-214">Int32</span></span>|  
|<span data-ttu-id="954b2-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="954b2-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="954b2-216">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-216">Int32</span></span>|  
|<span data-ttu-id="954b2-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="954b2-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="954b2-218">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-218">Int32</span></span>|  
|<span data-ttu-id="954b2-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-219">REMARKS</span></span>|<span data-ttu-id="954b2-220">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-220">String</span></span>|  
|<span data-ttu-id="954b2-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="954b2-222">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="954b2-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="954b2-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="954b2-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-224">ColumnName</span></span>|<span data-ttu-id="954b2-225">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="954b2-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="954b2-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-227">String</span></span>|  
|<span data-ttu-id="954b2-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="954b2-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="954b2-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-229">String</span></span>|  
|<span data-ttu-id="954b2-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="954b2-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-231">String</span></span>|  
|<span data-ttu-id="954b2-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-232">COLUMN_NAME</span></span>|<span data-ttu-id="954b2-233">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-233">String</span></span>|  
|<span data-ttu-id="954b2-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-234">COLUMN_TYPE</span></span>|<span data-ttu-id="954b2-235">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-235">Int16</span></span>|  
|<span data-ttu-id="954b2-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-236">DATA_TYPE</span></span>|<span data-ttu-id="954b2-237">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-237">Int16</span></span>|  
|<span data-ttu-id="954b2-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-238">TYPE_NAME</span></span>|<span data-ttu-id="954b2-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-239">String</span></span>|  
|<span data-ttu-id="954b2-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="954b2-240">COLUMN_SIZE</span></span>|<span data-ttu-id="954b2-241">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-241">Int32</span></span>|  
|<span data-ttu-id="954b2-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="954b2-243">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-243">Int32</span></span>|  
|<span data-ttu-id="954b2-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="954b2-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="954b2-245">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-245">Int16</span></span>|  
|<span data-ttu-id="954b2-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="954b2-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="954b2-247">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-247">Int16</span></span>|  
|<span data-ttu-id="954b2-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-248">NULLABLE</span></span>|<span data-ttu-id="954b2-249">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-249">Int16</span></span>|  
|<span data-ttu-id="954b2-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-250">REMARKS</span></span>|<span data-ttu-id="954b2-251">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-251">String</span></span>|  
|<span data-ttu-id="954b2-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="954b2-252">COLUMN_DEF</span></span>|<span data-ttu-id="954b2-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-253">String</span></span>|  
|<span data-ttu-id="954b2-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="954b2-255">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-255">Int16</span></span>|  
|<span data-ttu-id="954b2-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="954b2-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="954b2-257">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-257">Int16</span></span>|  
|<span data-ttu-id="954b2-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="954b2-259">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-259">Int32</span></span>|  
|<span data-ttu-id="954b2-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="954b2-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="954b2-261">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-261">Int32</span></span>|  
|<span data-ttu-id="954b2-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-262">IS_NULLABLE</span></span>|<span data-ttu-id="954b2-263">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-263">String</span></span>|  
|<span data-ttu-id="954b2-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="954b2-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="954b2-265">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-265">String</span></span>|  
|<span data-ttu-id="954b2-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="954b2-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="954b2-267">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-267">String</span></span>|  
|<span data-ttu-id="954b2-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="954b2-269">Byte</span><span class="sxs-lookup"><span data-stu-id="954b2-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="954b2-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="954b2-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="954b2-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-271">ColumnName</span></span>|<span data-ttu-id="954b2-272">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="954b2-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="954b2-274">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-274">String</span></span>|  
|<span data-ttu-id="954b2-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="954b2-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="954b2-276">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-276">String</span></span>|  
|<span data-ttu-id="954b2-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="954b2-278">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-278">String</span></span>|  
|<span data-ttu-id="954b2-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-279">COLUMN_NAME</span></span>|<span data-ttu-id="954b2-280">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-280">String</span></span>|  
|<span data-ttu-id="954b2-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-281">COLUMN_TYPE</span></span>|<span data-ttu-id="954b2-282">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-282">Int16</span></span>|  
|<span data-ttu-id="954b2-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-283">DATA_TYPE</span></span>|<span data-ttu-id="954b2-284">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-284">Int16</span></span>|  
|<span data-ttu-id="954b2-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-285">TYPE_NAME</span></span>|<span data-ttu-id="954b2-286">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-286">String</span></span>|  
|<span data-ttu-id="954b2-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="954b2-287">COLUMN_SIZE</span></span>|<span data-ttu-id="954b2-288">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-288">Int32</span></span>|  
|<span data-ttu-id="954b2-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="954b2-290">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-290">Int32</span></span>|  
|<span data-ttu-id="954b2-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="954b2-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="954b2-292">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-292">Int16</span></span>|  
|<span data-ttu-id="954b2-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="954b2-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="954b2-294">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-294">Int16</span></span>|  
|<span data-ttu-id="954b2-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-295">NULLABLE</span></span>|<span data-ttu-id="954b2-296">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-296">Int16</span></span>|  
|<span data-ttu-id="954b2-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-297">REMARKS</span></span>|<span data-ttu-id="954b2-298">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-298">String</span></span>|  
|<span data-ttu-id="954b2-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="954b2-299">COLUMN_DEF</span></span>|<span data-ttu-id="954b2-300">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-300">String</span></span>|  
|<span data-ttu-id="954b2-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="954b2-302">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-302">Int16</span></span>|  
|<span data-ttu-id="954b2-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="954b2-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="954b2-304">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-304">Int16</span></span>|  
|<span data-ttu-id="954b2-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="954b2-306">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-306">Int32</span></span>|  
|<span data-ttu-id="954b2-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="954b2-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="954b2-308">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-308">Int32</span></span>|  
|<span data-ttu-id="954b2-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-309">IS_NULLABLE</span></span>|<span data-ttu-id="954b2-310">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-310">String</span></span>|  
|<span data-ttu-id="954b2-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="954b2-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="954b2-312">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-312">String</span></span>|  
|<span data-ttu-id="954b2-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="954b2-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="954b2-314">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-314">String</span></span>|  
|<span data-ttu-id="954b2-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="954b2-316">Byte</span><span class="sxs-lookup"><span data-stu-id="954b2-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="954b2-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="954b2-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="954b2-318">Microsoft SQL Server драйвер ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="954b2-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="954b2-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="954b2-319">Tables</span></span>  
  
-   <span data-ttu-id="954b2-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="954b2-320">Columns</span></span>  
  
-   <span data-ttu-id="954b2-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="954b2-321">Procedures</span></span>  
  
-   <span data-ttu-id="954b2-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="954b2-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="954b2-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="954b2-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="954b2-324">Представления</span><span class="sxs-lookup"><span data-stu-id="954b2-324">Views</span></span>  
  
-   <span data-ttu-id="954b2-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="954b2-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="954b2-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="954b2-326">Tables and Views</span></span>  
  
|<span data-ttu-id="954b2-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-327">ColumnName</span></span>|<span data-ttu-id="954b2-328">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="954b2-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="954b2-330">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-330">String</span></span>|  
|<span data-ttu-id="954b2-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="954b2-331">TABLE_OWNER</span></span>|<span data-ttu-id="954b2-332">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-332">String</span></span>|  
|<span data-ttu-id="954b2-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-333">TABLE_NAME</span></span>|<span data-ttu-id="954b2-334">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-334">String</span></span>|  
|<span data-ttu-id="954b2-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-335">TABLE_TYPE</span></span>|<span data-ttu-id="954b2-336">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-336">String</span></span>|  
|<span data-ttu-id="954b2-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-337">REMARKS</span></span>|<span data-ttu-id="954b2-338">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="954b2-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="954b2-339">Columns</span></span>  
  
|<span data-ttu-id="954b2-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-340">ColumnName</span></span>|<span data-ttu-id="954b2-341">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="954b2-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="954b2-343">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-343">String</span></span>|  
|<span data-ttu-id="954b2-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="954b2-344">TABLE_OWNER</span></span>|<span data-ttu-id="954b2-345">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-345">String</span></span>|  
|<span data-ttu-id="954b2-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-346">TABLE_NAME</span></span>|<span data-ttu-id="954b2-347">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-347">String</span></span>|  
|<span data-ttu-id="954b2-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-348">COLUMN_NAME</span></span>|<span data-ttu-id="954b2-349">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-349">String</span></span>|  
|<span data-ttu-id="954b2-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-350">DATA_TYPE</span></span>|<span data-ttu-id="954b2-351">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-351">Int16</span></span>|  
|<span data-ttu-id="954b2-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-352">TYPE_NAME</span></span>|<span data-ttu-id="954b2-353">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-353">String</span></span>|  
|<span data-ttu-id="954b2-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="954b2-354">PRECISION</span></span>|<span data-ttu-id="954b2-355">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-355">Int32</span></span>|  
|<span data-ttu-id="954b2-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-356">LENGTH</span></span>|<span data-ttu-id="954b2-357">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-357">Int32</span></span>|  
|<span data-ttu-id="954b2-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="954b2-358">SCALE</span></span>|<span data-ttu-id="954b2-359">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-359">Int16</span></span>|  
|<span data-ttu-id="954b2-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="954b2-360">RADIX</span></span>|<span data-ttu-id="954b2-361">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-361">Int16</span></span>|  
|<span data-ttu-id="954b2-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-362">NULLABLE</span></span>|<span data-ttu-id="954b2-363">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-363">Int16</span></span>|  
|<span data-ttu-id="954b2-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-364">REMARKS</span></span>|<span data-ttu-id="954b2-365">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-365">String</span></span>|  
|<span data-ttu-id="954b2-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="954b2-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="954b2-367">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="954b2-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="954b2-368">Procedures</span></span>  
  
|<span data-ttu-id="954b2-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-369">ColumnName</span></span>|<span data-ttu-id="954b2-370">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="954b2-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="954b2-372">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-372">String</span></span>|  
|<span data-ttu-id="954b2-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="954b2-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="954b2-374">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-374">String</span></span>|  
|<span data-ttu-id="954b2-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="954b2-376">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-376">String</span></span>|  
|<span data-ttu-id="954b2-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="954b2-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="954b2-378">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-378">Int16</span></span>|  
|<span data-ttu-id="954b2-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="954b2-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="954b2-380">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-380">Int16</span></span>|  
|<span data-ttu-id="954b2-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="954b2-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="954b2-382">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-382">Int16</span></span>|  
|<span data-ttu-id="954b2-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-383">REMARKS</span></span>|<span data-ttu-id="954b2-384">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-384">String</span></span>|  
|<span data-ttu-id="954b2-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="954b2-386">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="954b2-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="954b2-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="954b2-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-388">ColumnName</span></span>|<span data-ttu-id="954b2-389">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="954b2-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="954b2-391">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-391">String</span></span>|  
|<span data-ttu-id="954b2-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="954b2-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="954b2-393">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-393">String</span></span>|  
|<span data-ttu-id="954b2-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="954b2-395">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-395">String</span></span>|  
|<span data-ttu-id="954b2-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-396">COLUMN_NAME</span></span>|<span data-ttu-id="954b2-397">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-397">String</span></span>|  
|<span data-ttu-id="954b2-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-398">COLUMN_TYPE</span></span>|<span data-ttu-id="954b2-399">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-399">Int16</span></span>|  
|<span data-ttu-id="954b2-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-400">DATA_TYPE</span></span>|<span data-ttu-id="954b2-401">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-401">Int16</span></span>|  
|<span data-ttu-id="954b2-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-402">TYPE_NAME</span></span>|<span data-ttu-id="954b2-403">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-403">String</span></span>|  
|<span data-ttu-id="954b2-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="954b2-404">PRECISION</span></span>|<span data-ttu-id="954b2-405">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-405">Int32</span></span>|  
|<span data-ttu-id="954b2-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-406">LENGTH</span></span>|<span data-ttu-id="954b2-407">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-407">Int32</span></span>|  
|<span data-ttu-id="954b2-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="954b2-408">SCALE</span></span>|<span data-ttu-id="954b2-409">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-409">Int16</span></span>|  
|<span data-ttu-id="954b2-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="954b2-410">RADIX</span></span>|<span data-ttu-id="954b2-411">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-411">Int16</span></span>|  
|<span data-ttu-id="954b2-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-412">NULLABLE</span></span>|<span data-ttu-id="954b2-413">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-413">Int16</span></span>|  
|<span data-ttu-id="954b2-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-414">REMARKS</span></span>|<span data-ttu-id="954b2-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-415">String</span></span>|  
|<span data-ttu-id="954b2-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="954b2-416">OVERLOAD</span></span>|<span data-ttu-id="954b2-417">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-417">Int32</span></span>|  
|<span data-ttu-id="954b2-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="954b2-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="954b2-419">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="954b2-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="954b2-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="954b2-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="954b2-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="954b2-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="954b2-422">Tables</span></span>  
  
-   <span data-ttu-id="954b2-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="954b2-423">Indexes</span></span>  
  
-   <span data-ttu-id="954b2-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="954b2-424">Columns</span></span>  
  
-   <span data-ttu-id="954b2-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="954b2-425">Procedures</span></span>  
  
-   <span data-ttu-id="954b2-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="954b2-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="954b2-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="954b2-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="954b2-428">Представления</span><span class="sxs-lookup"><span data-stu-id="954b2-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="954b2-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="954b2-429">Tables and Views</span></span>  
  
|<span data-ttu-id="954b2-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-430">ColumnName</span></span>|<span data-ttu-id="954b2-431">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="954b2-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="954b2-433">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-433">String</span></span>|  
|<span data-ttu-id="954b2-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="954b2-434">TABLE_OWNER</span></span>|<span data-ttu-id="954b2-435">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-435">String</span></span>|  
|<span data-ttu-id="954b2-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-436">TABLE_NAME</span></span>|<span data-ttu-id="954b2-437">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-437">String</span></span>|  
|<span data-ttu-id="954b2-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-438">TABLE_TYPE</span></span>|<span data-ttu-id="954b2-439">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-439">String</span></span>|  
|<span data-ttu-id="954b2-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-440">REMARKS</span></span>|<span data-ttu-id="954b2-441">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="954b2-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="954b2-442">Columns</span></span>  
  
|<span data-ttu-id="954b2-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-443">ColumnName</span></span>|<span data-ttu-id="954b2-444">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="954b2-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="954b2-446">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-446">String</span></span>|  
|<span data-ttu-id="954b2-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="954b2-447">TABLE_OWNER</span></span>|<span data-ttu-id="954b2-448">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-448">String</span></span>|  
|<span data-ttu-id="954b2-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-449">TABLE_NAME</span></span>|<span data-ttu-id="954b2-450">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-450">String</span></span>|  
|<span data-ttu-id="954b2-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-451">COLUMN_NAME</span></span>|<span data-ttu-id="954b2-452">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-452">String</span></span>|  
|<span data-ttu-id="954b2-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-453">DATA_TYPE</span></span>|<span data-ttu-id="954b2-454">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-454">Int16</span></span>|  
|<span data-ttu-id="954b2-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-455">TYPE_NAME</span></span>|<span data-ttu-id="954b2-456">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-456">String</span></span>|  
|<span data-ttu-id="954b2-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="954b2-457">PRECISION</span></span>|<span data-ttu-id="954b2-458">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-458">Int32</span></span>|  
|<span data-ttu-id="954b2-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-459">LENGTH</span></span>|<span data-ttu-id="954b2-460">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-460">Int32</span></span>|  
|<span data-ttu-id="954b2-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="954b2-461">SCALE</span></span>|<span data-ttu-id="954b2-462">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-462">Int16</span></span>|  
|<span data-ttu-id="954b2-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="954b2-463">RADIX</span></span>|<span data-ttu-id="954b2-464">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-464">Int16</span></span>|  
|<span data-ttu-id="954b2-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-465">NULLABLE</span></span>|<span data-ttu-id="954b2-466">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-466">Int16</span></span>|  
|<span data-ttu-id="954b2-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-467">REMARKS</span></span>|<span data-ttu-id="954b2-468">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-468">String</span></span>|  
|<span data-ttu-id="954b2-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="954b2-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="954b2-470">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="954b2-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="954b2-471">Procedures</span></span>  
  
|<span data-ttu-id="954b2-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-472">ColumnName</span></span>|<span data-ttu-id="954b2-473">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="954b2-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="954b2-475">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-475">String</span></span>|  
|<span data-ttu-id="954b2-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="954b2-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="954b2-477">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-477">String</span></span>|  
|<span data-ttu-id="954b2-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="954b2-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-479">String</span></span>|  
|<span data-ttu-id="954b2-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="954b2-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="954b2-481">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-481">Int16</span></span>|  
|<span data-ttu-id="954b2-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="954b2-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="954b2-483">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-483">Int16</span></span>|  
|<span data-ttu-id="954b2-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="954b2-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="954b2-485">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-485">Int16</span></span>|  
|<span data-ttu-id="954b2-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-486">REMARKS</span></span>|<span data-ttu-id="954b2-487">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-487">String</span></span>|  
|<span data-ttu-id="954b2-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="954b2-489">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="954b2-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="954b2-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="954b2-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-491">ColumnName</span></span>|<span data-ttu-id="954b2-492">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="954b2-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="954b2-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-494">String</span></span>|  
|<span data-ttu-id="954b2-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="954b2-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="954b2-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-496">String</span></span>|  
|<span data-ttu-id="954b2-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="954b2-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-498">String</span></span>|  
|<span data-ttu-id="954b2-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-499">COLUMN_NAME</span></span>|<span data-ttu-id="954b2-500">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-500">String</span></span>|  
|<span data-ttu-id="954b2-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-501">COLUMN_TYPE</span></span>|<span data-ttu-id="954b2-502">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-502">Int16</span></span>|  
|<span data-ttu-id="954b2-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-503">DATA_TYPE</span></span>|<span data-ttu-id="954b2-504">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-504">Int16</span></span>|  
|<span data-ttu-id="954b2-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-505">TYPE_NAME</span></span>|<span data-ttu-id="954b2-506">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-506">String</span></span>|  
|<span data-ttu-id="954b2-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="954b2-507">PRECISION</span></span>|<span data-ttu-id="954b2-508">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-508">Int32</span></span>|  
|<span data-ttu-id="954b2-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-509">LENGTH</span></span>|<span data-ttu-id="954b2-510">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-510">Int32</span></span>|  
|<span data-ttu-id="954b2-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="954b2-511">SCALE</span></span>|<span data-ttu-id="954b2-512">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-512">Int16</span></span>|  
|<span data-ttu-id="954b2-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="954b2-513">RADIX</span></span>|<span data-ttu-id="954b2-514">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-514">Int16</span></span>|  
|<span data-ttu-id="954b2-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-515">NULLABLE</span></span>|<span data-ttu-id="954b2-516">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-516">Int16</span></span>|  
|<span data-ttu-id="954b2-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-517">REMARKS</span></span>|<span data-ttu-id="954b2-518">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-518">String</span></span>|  
|<span data-ttu-id="954b2-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="954b2-519">OVERLOAD</span></span>|<span data-ttu-id="954b2-520">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-520">Int32</span></span>|  
|<span data-ttu-id="954b2-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="954b2-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="954b2-522">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="954b2-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="954b2-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="954b2-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="954b2-524">ColumnName</span></span>|<span data-ttu-id="954b2-525">DataType</span><span class="sxs-lookup"><span data-stu-id="954b2-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="954b2-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="954b2-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="954b2-527">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-527">String</span></span>|  
|<span data-ttu-id="954b2-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="954b2-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="954b2-529">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-529">String</span></span>|  
|<span data-ttu-id="954b2-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="954b2-531">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-531">String</span></span>|  
|<span data-ttu-id="954b2-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-532">COLUMN_NAME</span></span>|<span data-ttu-id="954b2-533">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-533">String</span></span>|  
|<span data-ttu-id="954b2-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-534">COLUMN_TYPE</span></span>|<span data-ttu-id="954b2-535">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-535">Int16</span></span>|  
|<span data-ttu-id="954b2-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-536">DATA_TYPE</span></span>|<span data-ttu-id="954b2-537">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-537">Int16</span></span>|  
|<span data-ttu-id="954b2-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="954b2-538">TYPE_NAME</span></span>|<span data-ttu-id="954b2-539">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-539">String</span></span>|  
|<span data-ttu-id="954b2-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="954b2-540">COLUMN_SIZE</span></span>|<span data-ttu-id="954b2-541">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-541">Int32</span></span>|  
|<span data-ttu-id="954b2-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="954b2-543">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-543">Int32</span></span>|  
|<span data-ttu-id="954b2-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="954b2-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="954b2-545">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-545">Int16</span></span>|  
|<span data-ttu-id="954b2-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="954b2-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="954b2-547">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-547">Int16</span></span>|  
|<span data-ttu-id="954b2-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-548">NULLABLE</span></span>|<span data-ttu-id="954b2-549">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-549">Int16</span></span>|  
|<span data-ttu-id="954b2-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="954b2-550">REMARKS</span></span>|<span data-ttu-id="954b2-551">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-551">String</span></span>|  
|<span data-ttu-id="954b2-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="954b2-552">COLUMN_DEF</span></span>|<span data-ttu-id="954b2-553">Строковое</span><span class="sxs-lookup"><span data-stu-id="954b2-553">String</span></span>|  
|<span data-ttu-id="954b2-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="954b2-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="954b2-555">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-555">Int16</span></span>|  
|<span data-ttu-id="954b2-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="954b2-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="954b2-557">Int16</span><span class="sxs-lookup"><span data-stu-id="954b2-557">Int16</span></span>|  
|<span data-ttu-id="954b2-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="954b2-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="954b2-559">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-559">Int32</span></span>|  
|<span data-ttu-id="954b2-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="954b2-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="954b2-561">Int32</span><span class="sxs-lookup"><span data-stu-id="954b2-561">Int32</span></span>|  
|<span data-ttu-id="954b2-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="954b2-562">IS_NULLABLE</span></span>|<span data-ttu-id="954b2-563">String</span><span class="sxs-lookup"><span data-stu-id="954b2-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="954b2-564">См. также</span><span class="sxs-lookup"><span data-stu-id="954b2-564">See Also</span></span>  
 [<span data-ttu-id="954b2-565">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="954b2-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
