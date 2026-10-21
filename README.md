# gem5 Adaptive Barrier

`alteracoes-gem5.patch` implementa o núcleo do Projeto 2. Aplique
`complemento-p02.patch` e `fix-teste-smoke.patch` em seguida, todos sobre o
commit de `versao-base.txt`.

```sh
git apply alteracoes-gem5.patch
git apply complemento-p02.patch
git apply fix-teste-smoke.patch
cd workloads/p02 && make
./barrier_stress
python ../../configs/projetos/p02/campanha_p02.py ../../build/X86/gem5.opt --dry-run
```

Execute a campanha removendo `--dry-run`, depois extraia as execuções:

```sh
python configs/projetos/p02/extrai_p02.py m5out/p02 --csv p02.csv
```

O extrator falha se o monitor registrar saída antecipada ou evento inválido.
