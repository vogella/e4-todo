package de.vogella.e4.todo.provider;

import org.eclipse.jface.viewers.ITreeContentProvider;
import org.eclipse.jface.viewers.Viewer;

import de.vogella.e4.todo.model.Category;
import de.vogella.e4.todo.model.ITodoModel;

public class TodoContentProvider implements ITreeContentProvider {

	private ITodoModel model;

	@Override
	public void dispose() {
	}

	@Override
	public void inputChanged(Viewer viewer, Object oldInput, Object newInput) {
		this.model = (ITodoModel) newInput;
	}

	@Override
	public Object[] getElements(Object inputElement) {
		return model.getCategories().toArray();
	}

	@Override
	public Object[] getChildren(Object parentElement) {
		if (parentElement instanceof Category) {
			Category category = (Category) parentElement;
			return category.getTodos().toArray();
		}
		return null;
	}

	@Override
	public Object getParent(Object element) {
		return null;
	}

	@Override
	public boolean hasChildren(Object element) {
		if (element instanceof Category) {
			return true;
		}
		return false;
	}
}
