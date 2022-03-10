# Capture the Bot: Using Adversarial Examples to Improve CAPTCHA Robustness to Bot Attacks

Summary:
- Using a combination of adversarial techniques to beat auto captcha solvers.
- Main goal: maintain human recognition while 'bluffing' NN based solvers
- Combines 2 main techinques: unrecognisable images which are created offline by indirectly encoded evolutionary algos, and
- Adversarial patches of various sizes are generated to fool an ensemble of pretrained network architectures. These patches are superimposed onto the captcha images!

Experiments:
- Add their 2 techniques, see how often they are able to fool deep NN classifiers.
- Also, evaluated usability of the captcha by testing on humans, checking if they are solvable (success rate) and also looking at experience (qualitative measure of the task). High success rate ~85% and users said the captcha was easier due to the weird unrecognisable images being immediately eliminated from decision process.