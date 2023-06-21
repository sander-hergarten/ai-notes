| Model          | episode_id | environment | action           | step_type | next_step_type | reward             | discount | observation        |
| -------------- | ---------- | ----------- | ---------------- | --------- | -------------- | ------------------ | -------- | ------------------ |
| Autoencoder    |            |             |                  |           |                |                    |          | `Image`            |
| Sequence Rater |            |             | `tf.Tensor[int]` |           |                | `tf.Tensor[float]` |          | `tf.Tensor[Image]` |
|                |            |             |                  |           |                |                    |          |                    |

