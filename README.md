# master_tbank

**Автор:** Агафонов Павел Андреевич

## Описание

Реализован пайплайн дообучения компактной vision-and-language модели [NanoVLM](https://github.com/huggingface/nanoVLM) для управления агентом в среде [MiniGrid EmptyEnv](https://minigrid.farama.org/environments/minigrid/EmptyEnv/). Сравниваются три режима: SFT на экспертных BFS-траекториях, RL-дообучение через [GRPO](https://arxiv.org/abs/2402.03300) с прямым выводом действия и GRPO в формате **текст + действие**. Обучение проводится на картах 5×5, 6×6, 8×8; OOD-оценка — на 10×10 и 12×12.

## Результаты

| Метод | SR OOD ↑ | Steps до SR ≥ 0.50 |
|---|---:|---:|
| SFT (BFS) | 0.208 | — |
| SFT + Aug + LS | **0.667** | — |
| GRPO direct action | 0.500 | 960 |
| GRPO text+action | 0.533 | 960 |

## Запуск

Всё реализовано в одном ноутбуке — последовательный запуск ячеек сверху вниз воспроизводит полный эксперимент.
Также прикладываю ссылку на colab: https://colab.research.google.com/drive/1Hn4JGE3G0wqH_-vN0GUFCMid7e05-FCg?usp=sharing
