
install: 
	pip install -e .[dev]
	pre-commit install

test:
	pytest -s

cov:
	pytest --cov={{ cookiecutter.package_name }}

mypy:
	mypy . --ignore-missing-imports

pylint:
	pylint {{ cookiecutter.package_name }}

ruff:
	ruff --fix {{ cookiecutter.package_name }}/*.py

git-rm-merged:
	git branch -D `git branch --merged | grep -v \* | xargs`

update:
	pur

update-pre:
	pre-commit autoupdate --bleeding-edge

git-rm-merged:
	git branch -D `git branch --merged | grep -v \* | xargs`

release:
	git push
	git push origin --tags

build:
	rm -rf dist
	pip install build
	python -m build
