# Guia Prático

## ✅ Passo 1: Instale as extensões no VS Code
> Procure e instale estas:
- Modern Fortran
- CodeLLDB
- Fortran IntelliSense (opcional)

## ✅ Passo 2: Compile seu código com flags de debug
> No terminal do VS Code:
```bash
gfortran -g matriz_vetores.f90 -o matriz_vetores
```
_A flag -g inclui símbolos de debug._

## ✅ Passo 3: Estrutura da pasta
> Organize seu projeto assim:
```bash
/seu-projeto
│
├── matriz_vetores.f90
└── .vscode/
    └── launch.json
```

##✅ Passo 4: launch.json para Fortran com gfortran + LLDB
> Crie o arquivo .vscode/launch.json com o seguinte conteúdo:
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Fortran (GDB)",
      "type": "cppdbg",
      "request": "launch",
      "program": "${workspaceFolder}/matriz_vetores",
      "args": [],
      "stopAtEntry": false,
      "cwd": "${workspaceFolder}",
      "environment": [],
      "externalConsole": false,
      "MIMode": "gdb",
      "miDebuggerPath": "gdb",
      "preLaunchTask": "build"
    }
  ]
}
```

## ✅ Passo 5: Tarefa de build (tasks.json)
> Também crie o arquivo .vscode/tasks.json para compilar automaticamente:
```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "build",
      "type": "shell",
      "command": "gfortran",
      "args": [
        "-g",
        "matriz_vetores.f90",
        "-o",
        "matriz_vetores"
      ],
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "problemMatcher": []
    }
  ]
}
```

## ✅ Debug passo a passo
1. Pressione Ctrl+Shift+D (painel de debug).
2. Selecione "Debug Fortran".
3. Pressione **F5** para iniciar.
4. Você pode adicionar breakpoints, ver variáveis locais, pilha de chamadas, etc.
