python_requirements(source="pyproject.toml", name="reqs")

python_sources(
    name = "src",
    sources = ["./src/foo_project/**/*.py"],
    dependencies = [
        ":reqs",
    ],
)

resource(name="pyproject", source="pyproject.toml")

python_distribution(
    name="mydist",
    dependencies=[
        ":pyproject",
        ":src"
        # Dependencies on code to be packaged into the distribution.
    ],
    provides=python_artifact(
        name="foo_project",
        version="0.1.0",
    ),
    generate_setup = False,
)

python_tests(
    name = "foo_tests",
    sources = ["./tests/**/*.py"],
    dependencies = [
        ":mydist",
    ],
    runtime_package_dependencies = [":mydist"]
)


