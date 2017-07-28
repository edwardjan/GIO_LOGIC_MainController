package logic;

import java.awt.EventQueue;
import java.util.ArrayList;

import data.Project;
import gui.MainFrame;
import gui.ProjectDetailsPanel;
import gui.ProjectListPanel;

public class MainController {
	private MainFrame mainFrame;
	private ProjectListPanel projectListPanel;
	private ProjectDetailsPanel projectDetailsPanel;
	private ProjectDataHandler projectDataHandler;

	public MainController() {
		mainFrame = new MainFrame(this);
		projectListPanel = new ProjectListPanel(this);
		projectDetailsPanel = new ProjectDetailsPanel(this);
		projectDataHandler = new ProjectDataHandler();

	}

	public void start() {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					mainFrame.setVisible(true);
					mainFrame.setPanel(projectListPanel);
					projectListPanel.displayProjects(getProjectList());
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	public void returnToProjectList() {
		mainFrame.setPanel(projectListPanel);
	}

	public Project getProjectDetails(String projectID) {
		return null;
	}

	public ArrayList<Project> getProjectList() {
		System.out.println("In ProjectList()");
		projectDataHandler.getProcessedProjectList();
		return projectDataHandler.getProcessedProjectList();
	}

	public void displayProjectDetails(String string) {
		// TODO Auto-generated method stub
		mainFrame.setPanel(projectDetailsPanel);

	}
}
