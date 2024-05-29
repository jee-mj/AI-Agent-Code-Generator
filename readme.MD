# `llama-cpp-python` fails to build via Devenv

You could probably try to just pull the dependencies with pip.

Dependencies were added to 'pyproject.toml` by poetry by utilising the script below:

```sh
cat requirements.txt | while read -l line
    set parts (string split '==' $line)
    poetry add $parts[1]@$parts[2]
end
```

## Replicate issue

You should be able to replicate the issue by just running `poetry add llama-cpp-python` after cloning in and activating the devenv.
