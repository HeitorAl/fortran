# Guia Prático

## ✅ Passo 1: Instale as extensões no VS Code
> Procure e instale estas:
- Modern Fortran
- CodeLLDB
- Fortran IntelliSense (opcional)

## ✅ Passo 2: Compile seu código com flags de debug
> No terminal do VS Code:
```
gfortran -g matriz_vetores.f90 -o matriz_vetores
```
_A flag -g inclui símbolos de debug._

## ✅ Debug passo a passo
1. Pressione Ctrl+Shift+D (painel de debug).
2. Selecione "Debug Fortran".
3. Pressione **F5** para iniciar.
4. Você pode adicionar breakpoints, ver variáveis locais, pilha de chamadas, etc.
