#################################################
#												
# File - Makefile								
# Team name - BRAINSTORM						
# Authors - Frantisek Fúdor < xfudor00 >		
#		  - Andrej Rázus < xrazus00 >			
#		  - Oto Málik < xmalik22 >				
#												
#################################################

VisualStudioPath=C:\Program Files (x86)\Microsoft Visual Studio\2019\Community
Build=C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Current\Bin
Dir=$(shell cd)\..
MSBuild=MSBuild\Current\Bin\MSBuild.exe
TEST=Common7\IDE\CommonExtensions\Microsoft\TestWindow\vstest.console.exe

# Project preparation
ProjectName=ivs_proj_2_calc
ProjectDir=$(Dir)\$(ProjectName)
Project=$(ProjectDir)\bin\Debug\$(ProjectName).exe
ProjectFile=$(ProjectDir)\$(ProjectName).csproj

# Pack preparation
PackName=xfudor00_xrazus00_xmalik22
#1
PDir=$(Dir)\..\$(PackName)
PDocuments=$(PDir)\Documents
PArch=$(Dir)\$(PackName).zip
PRepozit=$(PDir)\vs_proj_2_calc

# Test preparation
TestName=UnitTests
TestDir=$(Dir)\$(TestName)
TestFile=$(TestDir)\$(TestName).csproj
TestFinallDir=$(Dir)\TestsRating
TestFinallFile=$(TestFinallDir)\Rating
TestSpace=C:\Users\my bro\Desktop\VUT\IVS\projekt2\ivs_proj_2_calc-master\UnitTests\bin\Debug\UnitTests.dll
HelpFile=$(ProjectDir)\HelpFile.txt

RemoveFiles="$(Dir)\ivs_proj_2_calc.sln" "$(ProjectDir)\$(ProjectName).csproj" "$(TestDir)\$(TestName).csproj" 


#Pack preparation


.PHONY: all build pack clean run help profile maketest Test

all: build

build:
	cd "$(VisualStudioPath)" & $(MSBuild) "$(ProjectFile)" 

#pack:
#	mkdir "$(PDir)"
#	mkdir "$(PDocuments)"

#clean:

run: all

Test: maketest
	if exist "$(TestFinallFile)" del "$(TestFinallFile)"
	if not exist "$(TestFinallDir)" mkdir "$(TestFinallDir)"
	cd "$(VisualStudioPath)" & $(TEST) "$(TestSpace)" /logger:trx;LogFileName="$(TestFinallFile)".trx

maketest: 
	cd "$(VisualStudioPath)" & $(MSBuild) "$(TestFile)"
	
help:
	"$(HelpFile)"


#vstest.console.exe  myTestFile.dll /Settings:Local.RunSettings  /Logger:trx
# gnuwin32 stiahnut prekopirovat subory do priecinku s Makefile
# nalinkovat MSBuild z visualka do Path 
# read me "stiahnut virtual studio"
#C:\Program Files (x86)\Microsoft Visual Studio\2019\Community
#Install-Package NUnit3TestAdapter 
#Install-Package NUnitTestAdapter
#C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Current\Bin